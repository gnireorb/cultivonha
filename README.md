# r/Cultivonha

Site estático em Jekyll com a wiki da comunidade [r/Cultivonha](https://www.reddit.com/r/Cultivonha/), em pt-BR e adaptada ao Brasil.

## Rodar localmente (Windows)

1. Instale o **Ruby+Devkit 3.4 (x64)** de rubyinstaller.org e, no fim, rode `ridk install` com a opção 3.
2. Instale o **Node.js LTS** de nodejs.org (usado para gerar a busca).
3. Na pasta do projeto, rode `bundle install` uma vez.

O `jekyll serve` sozinho atualiza as páginas enquanto você edita, mas não gera a busca. Se criar ou editar páginas, rode esses comandos para a busca incluí-las.

```bat
bundle exec jekyll build
npx -y pagefind --site _site
bundle exec jekyll serve
```

## Estrutura

```
_config.yml              nome do site, link do Reddit, repositório (para "Sugerir uma correção")
_data/navegacao.yml      menu lateral: seções, cores e a ordem das páginas
_data/glossario.yml      glossário (página /glossario/ e script de tradução)
_data/fotoperiodo.yml    horas de luz por cidade (gerado por tools/fotoperiodo.py)
_data/diagnostico.yml    Diagnóstico: perguntas, causas, fotos, substratos, pH/EC e a tabela de Deficiências
_data/doses.yml          calculadora de dose: produtos, doses e estudos de referência
_wiki/                   páginas da wiki (→ /<pagina>/, índice em /indice/)
_layouts/doc.html        layout de leitura: menu | texto | "Nesta página"
_includes/               topo, rodapé, menu lateral, anterior/próxima, índice da wiki
assets/css/main.css      tema (claro e escuro), cores das seções
assets/js/site.js        tema, menu no celular, busca, índice da página
assets/fonts/            Young Serif e Atkinson Hyperlegible Next, auto-hospedadas (licença OFL)
tools/                   importador da wiki, tradução, fotoperíodo, prévias, miniaturas e verificação
```

## Organizar a wiki

O menu lateral, a página inicial e o índice da wiki saem todos de `_data/navegacao.yml`. Para mudar a ordem, mover uma página de seção ou criar uma seção nova, edite só esse arquivo.

Cores disponíveis para as seções: `musgo`, `led`, `ar`, `terra`, `folha`, `broto`, `alerta`, `tricoma`, `sol`, `ardosia`. Elas são definidas no topo de `assets/css/main.css`.

Campos úteis no topo de cada página:

```yaml
title: "Título completo da página"
titulo_curto: "Nome no menu"        # opcional
description: "Uma frase dizendo o que a página resolve."
nota_atualizacao: "..."             # opcional: caixa de aviso no topo
toc: false                          # opcional: esconde o "Nesta página"
```

Uma página da wiki que não esteja em `navegacao.yml` aparece no menu em "Outras páginas".

## Atualizar a wiki a partir do Reddit

O Reddit bloqueia o acesso anônimo à API (erro 403), então a exportação é feita no seu navegador:

1. Entre em reddit.com, aperte F12 e abra a aba Console. Na primeira vez, o Chrome pede para você digitar `allow pasting`.
2. Cole o conteúdo de `tools/exportar_wiki_navegador.js` e aperte Enter. O navegador baixa `wiki-Cultivonha.json`.
3. Rode:

```bat
python tools\importar_wiki_reddit.py Cultivonha --de-arquivo %USERPROFILE%\Downloads\wiki-Cultivonha.json --historico
```

O importador não sobrescreve páginas que já existem, para não perder títulos, descrições e ajustes feitos aqui. Use `--forcar` para trazer de novo o texto do Reddit. Depois, acrescente as páginas novas em `_data/navegacao.yml`.

## Imagens

Um link para imagem sozinho numa linha vira uma figura com legenda, feita por `_plugins/imagens.rb`:

```markdown
[Imagem do VPD chart no HAOS](https://www.reddit.com/media?url=https%3A%2F%2Fi.redd.it%2F9foy13o353ga1.jpg)
```

Isso funciona com links do visualizador do Reddit (`reddit.com/media?url=…`), `i.redd.it`, `preview.redd.it`, `i.imgur.com` ou qualquer endereço terminado em `.jpg`, `.png`, `.gif` ou `.webp`. Também vale a sintaxe normal de imagem: `![legenda](endereço)`. Um link de imagem no meio de uma frase continua como link.

Para guardar as imagens no próprio site, de modo que não sumam se o post do Reddit for apagado, rode:

```bat
python tools\baixar_imagens.py
```

As imagens vão para `assets/img/` e os links das páginas passam a apontar para lá. Rode de novo depois de cada importação da wiki.

## Antes de subir o site

Depois de editar páginas ou fotos, rode, de dentro da pasta `site/`:

```bat
python tools\cards_caso.py
python tools\miniaturas.py
bundle exec jekyll build
python tools\verificar.py
```

- `cards_caso.py` desenha a prévia do Reddit de cada card de foto (`/caso/<foto>/`).
- `miniaturas.py` gera as versões leves (WebP) das fotos, usadas no Diagnóstico.
- `verificar.py` confere links e âncoras quebrados, imagens faltando, os dados do Diagnóstico e da calculadora, doses diferentes entre o texto e a calculadora e páginas com o texto mudado sem trocar o `atualizado:`. Se aparecer **ERRO**, corrija antes de subir; os **avisos** não impedem.

Card que mostra um problema coberto pelo Diagnóstico (deficiência, excesso, praga, luz, calor, fim de ciclo) pode ganhar `data-causa="potassio"` no `<figure>`, com os ids de `causas` em `_data/diagnostico.yml`. Ele passa a aparecer como caso do sub no resultado.

## Escrever uma página

Copie `tools/modelo-pagina.md` para `_wiki/<nome>.md`, preencha o topo (inclusive `fontes`, no padrão ABNT) e acrescente o endereço `/<nome>/` em `_data/navegacao.yml`. Para usar a tabela de horas de luz:

`{% include tabela-fotoperiodo.html cidades="Recife,Brasília,Curitiba" %}`

## Traduzir textos (opcional)

`tools/pipeline.py` converte HTML em Markdown, traduz com a API do Claude usando o glossário e revisa termos e unidades. Só traduz arquivos com licença ou autorização registrada em `origem.licenca`. Detalhes em `python tools/pipeline.py --help`.

**Grow Weed Easy:** a tradução das páginas do site foi autorizada por e-mail em outubro de 2026 (resposta de Sirius Fourside), com uma condição: cada página traduzida precisa ter um link para a original. Ao converter, use:

```bat
python tools\pipeline.py converter <arquivo> entrada\md\ --licenca "Autorizado pelo Grow Weed Easy por e-mail (out. 2026), com link para o original"
```

e confira se `origem.url` aponta para a página em inglês. O layout mostra essa linha, com o link, no fim de toda página que tem `origem`. O e-mail fica guardado com a moderação; não publique endereços.
