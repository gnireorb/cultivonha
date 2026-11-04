---
title: "Cultivo outdoor no Brasil: calendário, fotoperíodo e clima"
titulo_curto: Cultivo outdoor no Brasil
description: Por que os calendários estrangeiros não funcionam aqui, quantas horas de luz sua cidade realmente tem e qual estratégia faz sentido em cada região.
tempo_leitura: 18
atualizado: '2026-10-27'
revisao: "Página da wiki desde outubro de 2026 (antes ficava na seção Guias)."
fontes_acesso: 2026-10-16
fontes:
  - abnt: "CAMARGO, P.; PANDOLFO, C.; BOSCO, L. C. Análise de risco climático para *Cannabis* spp. para Santa Catarina. **Agrometeoros**, Passo Fundo, v. 32, e027692, 2024. Disponível em: <https://apct.sede.embrapa.br/agrometeoros/article/download/27692/15350/133393>."
    nota: "Janela de geada, limiar de 14 h de luz e soma térmica por região de SC."
  - abnt: "CHANDRA, S.; LATA, H.; KHAN, I. A.; ELSOHLY, M. A. Photosynthetic response of *Cannabis sativa* L. to variations in photosynthetic photon flux densities, temperature and CO<sub>2</sub> conditions. **Physiology and Molecular Biology of Plants**, [S. l.], v. 14, n. 4, p. 299-306, 2008. DOI: <https://doi.org/10.1007/s12298-008-0027-x>."
    nota: "Fotossíntese máxima por volta de 30 °C; acima disso, os estômatos fecham e a eficiência no uso da água cai."
  - abnt: "CHANDRA, S.; LATA, H.; KHAN, I. A.; ELSOHLY, M. A. Temperature response of photosynthesis in different drug and fiber varieties of *Cannabis sativa* L. **Physiology and Molecular Biology of Plants**, [S. l.], v. 17, n. 3, p. 297-303, 2011. DOI: <https://doi.org/10.1007/s12298-011-0068-4>."
    nota: "Temperatura ótima de 30 a 35 °C numa variedade mexicana e de cerca de 25 °C em outras."
  - abnt: "HAZE, N. Dealing with heat and humidity outdoors. **Grow Weed Easy**, [S. l.], [20--]. Disponível em: <https://www.growweedeasy.com/dealing-with-heat-and-humidity-outdoors>."
    nota: "Cuidados com calor, umidade e podridão de flor."
  - abnt: "HAZE, N. How to grow cannabis outdoors (easier method). **Grow Weed Easy**, [S. l.], [20--]. Disponível em: <https://www.growweedeasy.com/beginner-guide-to-growing-cannabis-outdoors>."
    nota: "Base geral sobre automáticas e fotoperiódicas, horas de sol direto e cuidados com mofo, adaptada para as latitudes brasileiras."
  - abnt: "SPENCER, J. W. Fourier series representation of the position of the sun. **Search**, Sydney, v. 2, n. 5, p. 172, 1971."
    nota: "Fórmula da declinação solar usada no cálculo das horas de luz (tools/fotoperiodo.py), com precisão de poucos minutos."
    sem_acesso: true
  - abnt: "ZHANG, M.; ANDERSON, S. L.; BRYM, Z. T.; PEARSON, B. J. Photoperiodic flowering response of essential oil, grain, and fiber hemp (*Cannabis sativa* L.) cultivars. **Frontiers in Plant Science**, Lausanne, v. 12, art. 694153, 2021. DOI: <https://doi.org/10.3389/fpls.2021.694153>."
    nota: "Fotoperíodo crítico por variedade (13 h 45 a 15 h 30) e efeito do crepúsculo sobre a floração."
---

> **Resumo**
> - Os guias estrangeiros são escritos para lugares onde o dia de verão passa de 15 ou 16 horas. **No Brasil, o dia mais longo do ano vai de cerca de 12 h no Norte a pouco mais de 14 h no extremo Sul.**
> - Muitas variedades fotoperiódicas precisam de 14 h ou mais de luz para continuar vegetando. Por isso, **em boa parte do Brasil elas começam a florir logo depois de ir para fora**, ainda pequenas.
> - **Norte, Nordeste e Centro-Oeste:** automáticas são o caminho mais simples. A época é definida pela chuva, não pela luz.
> - **Sul e litoral do Sudeste:** fotoperiódicas funcionam se forem para fora em setembro ou outubro, depois do risco de geada. A colheita cai entre março e abril, junto com as chuvas de fim de verão.

<figure class="imagem">
  <a href="{{ '/assets/img/wiki/outdoor-estufa-tunel.jpg' | relative_url }}"><img src="{{ '/assets/img/wiki/outdoor-estufa-tunel.jpg' | relative_url }}" width="1200" height="800" loading="lazy" alt="Plantas de cannabis cultivadas no solo, sob os arcos de uma estufa em túnel ainda sem plástico"></a>
  <figcaption><strong>Estufa em túnel (<em>hoop house</em>).</strong> Os arcos recebem plástico na época de chuva, o que ajuda a proteger as flores da água e dos fungos. Foto: Brian Shamblen, <a href="https://commons.wikimedia.org/wiki/File:Cannabis_plants_in_hoop_house.jpg" rel="noopener">CC BY 2.0</a>, via Wikimedia Commons.</figcaption>
</figure>

## Por que os calendários estrangeiros não servem aqui

Quase todo material de cultivo em inglês foi escrito por e para quem mora entre 35° e 50° de latitude norte: Califórnia, Colorado, Canadá, Europa. Nesses lugares, o dia em junho é muito longo:

| Latitude | Exemplo | Dia mais longo | Com crepúsculo |
|---|---|---|---|
| 40°N | Nova York, Madri | 15h01 | 16h07 |
| 45°N | Montreal, Turim | 15h37 | 16h52 |
| 50°N | Londres (aprox.), Praga | 16h22 | 17h52 |
| 23,5°S | São Paulo | 13h35 | 14h26 |
| 3°S | Manaus | 12h18 | 13h03 |

Uma planta fotoperiódica plantada em maio em Madri passa semanas recebendo 15 a 16 horas de luz. Ela entende isso como "ainda é verão, continue crescendo" e vira um arbusto antes de florir.

A regra prática de "inverter os meses" também não resolve. Alguns guias sugerem, para o hemisfério sul, ir para fora no fim de outubro ou início de novembro. Isso funciona na Nova Zelândia ou no sul da Argentina, que estão em latitudes parecidas com as da Europa. No Brasil, mesmo em novembro, o dia simplesmente não fica longo o bastante na maior parte do território.

## Quantas horas de luz sua cidade tem

A tabela mostra a duração do dia (do nascer ao pôr do sol) no dia 15 de cada mês. As células verdes indicam 14 h ou mais.

{% include tabela-fotoperiodo.html %}

Repare em três coisas:

1. **Do Norte até Salvador, o dia nunca chega a 13 h.** Em Macapá ele é praticamente igual o ano todo.
2. **Em Brasília e Cuiabá, o máximo é cerca de 13 h**, por poucas semanas em dezembro.
3. **Só no Rio Grande do Sul o dia passa de 14 h**, e mesmo assim por poucas semanas em volta do solstício (21 de dezembro).

### O crepúsculo conta

A planta não "desliga" no pôr do sol. O estudo da Universidade da Flórida (Zhang *et al.*, 2021) mediu que a luz fraca do crepúsculo civil já é suficiente para influenciar a floração. Na prática, some de 45 a 60 minutos aos valores da tabela. Com isso, São Paulo chega a cerca de 14 h 25 no fim de dezembro, e Porto Alegre a cerca de 15 h.

O mesmo vale para luz artificial: poste, refletor do vizinho ou lâmpada da varanda acesa à noite podem atrasar ou bagunçar a floração de uma fotoperiódica.

## O fotoperíodo crítico de cada variedade

**Fotoperíodo crítico** é a duração do dia abaixo da qual a planta fotoperiódica para de vegetar e começa a florir. Ele não é igual para todas:

- No estudo da Flórida, as variedades ricas em canabinoides tiveram fotoperíodo crítico entre **13 h 45 e 15 h 30**. Algumas variedades de fibra eram praticamente indiferentes à luz.
- **Quinze minutos fazem diferença.** Várias plantas atrasaram de 5 a 13 dias a floração só por passar de 13 h 45 para 14 h de luz.
- **O nome da variedade não garante o comportamento.** Sementes com o mesmo nome, vindas de fornecedores diferentes, responderam de forma diferente.

Compare esses números com a tabela acima: **na maior parte do Brasil, o dia fica abaixo do fotoperíodo crítico da maioria das variedades o ano inteiro.** Por isso a planta começa a florir assim que vai para fora, seja qual for o mês.

Genéticas de origem tropical, que evoluíram com dias de cerca de 12 horas, tendem a lidar melhor com isso, mas costumam ter floração mais longa. Se você não sabe a origem da genética, trate-a como sensível.

## Genéticas para calor e clima tropical

Calor sozinho raramente mata a planta. O problema costuma ser o calor junto com umidade alta, chuva na floração e sol forte no vaso. A genética certa ajuda nas três coisas.

### Quanto calor a planta aguenta

Em medições da Universidade do Mississippi, a fotossíntese da cannabis foi máxima por volta de **30 °C**. Acima disso, os estômatos (os poros da folha) começaram a fechar e a planta passou a gastar mais água para produzir menos (Chandra *et al.*, 2008). A variedade varia: numa comparação entre plantas de origens diferentes, uma variedade mexicana teve o ponto ótimo entre **30 e 35 °C**, enquanto outras ficaram em torno de **25 °C** (Chandra *et al.*, 2011).

Na prática:

- **Até uns 30 °C:** a maioria das genéticas vai bem, se tiver água.
- **De 30 a 35 °C:** as genéticas de origem tropical continuam crescendo. As outras desaceleram, e as folhas podem se curvar para cima, como uma canoa.
- **Acima de 35 °C:** quase todas sofrem. Na floração, o calor pode fazer a flor soltar "torres" de cálices novos (*foxtail*) e perder aroma. Veja [Estresse]({{ '/estresse/' | relative_url }}).

### O que procurar na descrição

| Característica | Por que importa no Brasil |
|---|---|
| **Origem tropical** (de lugares perto do Equador) | Evoluiu com calor, umidade e dias de 12 horas. Costuma tolerar melhor 30 a 35 °C. |
| **Flores mais soltas, menos compactas** | Secam mais rápido depois da chuva e do orvalho. A flor densa e pesada é a que mais apodrece por dentro. |
| **Folhas finas e entrenós espaçados** | O vento passa pela copa, e a umidade não fica presa. |
| **Descrita como resistente a fungos** | Ajuda contra podridão de flor e oídio, os maiores riscos do verão chuvoso. |
| **Tempo de floração compatível com a sua janela** | Tropicais puras podem levar de 12 a 16 semanas só de floração. Confira se o ciclo termina antes do pior mês de chuva ou do frio. |

### Genéticas mais bem avaliadas para o calor

São as genéticas que os cultivadores de clima quente e úmido mais citam como confiáveis. Os tempos são aproximados e mudam de um fornecedor para outro. **O nome não garante o comportamento**: depois de décadas de cruzamentos, duas sementes com o mesmo nome podem dar plantas bem diferentes (veja [Genéticas]({{ '/geneticas/' | relative_url }})). A wiki não indica bancos de sementes nem recebe nada por isso.

**Para começar: rápidas e resistentes**

| Genética | Origem | Floração* | Por que é bem avaliada | Atenção |
|---|---|---|---|---|
| **Durban Poison** | África do Sul | 8 a 10 semanas | Aguenta calor, flor solta e resistente a fungos, e termina rápido para uma sativa. É a mais citada para clima tropical. | Estica bastante; precisa de altura. |
| **Jack Herer** | Híbrida de base Haze | 9 a 10 semanas | Tolera calor e umidade, e é estável. | Alguns fenótipos têm flor mais densa. |
| **Green Crack** | Híbrida de base sativa | 7 a 9 semanas | Uma das sativas mais rápidas. Boa para fechar o ciclo antes do pico de chuva. | Pede rega regular no calor. |
| **Early Skunk** | Híbrida (Skunk × Early Pearl) | 7 a 8 semanas | Criada para outdoor; termina cedo e resiste a fungos. | Flor mais compacta; vigie depois da chuva. |
| **Frisian Dew** | Híbrida, criada para outdoor | 7 a 8 semanas | Referência em resistência a fungos em clima úmido. | Menos tolerante a calor extremo que as tropicais. |

**Sativas de base Haze: produzem muito, mas demoram mais**

| Genética | Origem | Floração* | Por que é bem avaliada | Atenção |
|---|---|---|---|---|
| **Amnesia Haze** | Híbrida de base tropical | 10 a 12 semanas | Muito tolerante ao calor, flor alongada e arejada. | Planta alta; ciclo longo. |
| **Super Silver Haze** | Híbrida (Skunk × Northern Lights × Haze) | 10 a 11 semanas | Equilíbrio entre vigor tropical e flor mais firme. | Estica muito no início da floração. |
| **Super Lemon Haze** | Híbrida de base Haze | 9 a 10 semanas | Aguenta calor e tem boa resistência a oídio. | Precisa de espaço lateral. |

**Tropicais puras (linhagens tradicionais): para quem tem paciência e espaço**

| Genética | Origem | Floração* | Por que é bem avaliada | Atenção |
|---|---|---|---|---|
| **Thai** | Tailândia | 12 a 16 semanas | Feita para calor e umidade; flor bem solta. | Muito longa e alta; difícil em vaso. |
| **Punto Rojo / Colombian Gold** | Colômbia | 12 a 14 semanas | Evoluiu perto do Equador; aguenta calor e chuva. | Ciclo longo. |
| **Malawi** | Malawi | 14 a 18 semanas | Muito resistente a calor e fungos. | Das mais demoradas; pode passar de 3 m. |
| **Lamb's Bread / jamaicanas** | Jamaica | 10 a 12 semanas | Clima parecido com o do Nordeste brasileiro. | Linhagens pouco padronizadas. |

**Automáticas para calor**

As automáticas não aguentam mais calor por serem automáticas, mas as versões com base sativa se saem melhor. As mais citadas são as versões automáticas de **Durban Poison**, **Amnesia Haze**, **Green Crack** e **Jack Herer**. No Norte e no Nordeste, a **Northern Lights automática** também é muito relatada, apesar de ser de base índica: é compacta e fácil, mas tem flor densa, então prefira a estação seca. Todas levam de 10 a 12 semanas desde a semente.

\*Floração: semanas desde as primeiras flores até a colheita, para fotoperiódicas.

**Qual escolher:**

- **Norte e Nordeste:** uma Haze automática ou a Durban Poison, se puder vegetar sob luz.
- **Centro-Oeste, na seca:** qualquer uma das automáticas acima.
- **Sul e litoral do Sudeste:** Durban Poison, Early Skunk ou Frisian Dew, que terminam antes das chuvas de março.
- **Muito espaço e paciência:** as tropicais puras.

Sobre as genéticas brasileiras: as sementes encontradas no prensado vêm, em geral, de plantas cultivadas no Nordeste (como na região do chamado "Polígono da Maconha"), que já estão adaptadas ao calor. Mas a origem é desconhecida, a maioria sai macho, e muitas vêm polinizadas por hermafroditas. Trate como uma loteria. Veja [Machos e hermafroditas]({{ '/sexagem/' | relative_url }}).

### E as automáticas?

No Norte, no Nordeste e no Centro-Oeste, a automática continua sendo a escolha mais simples, porque não depende da luz. Elas não são, por si só, mais resistentes ao calor, mas o ciclo curto (10 a 12 semanas) permite encaixar o cultivo na época mais seca e menos quente. Muitas automáticas são cruzadas com genéticas tropicais. Quando a descrição falar em "dominância sativa", flores soltas ou resistência a fungos, é um bom sinal para o nosso clima.

### Ajudando a planta no calor

- **Raízes frescas:** o vaso preto ao sol pode passar de 40 °C por dentro. Use vaso claro, coloque um vaso dentro do outro, enterre parte dele ou faça sombra só na base. Vasos de feltro e vasos maiores esquentam menos.
- **Água na hora certa:** regue de manhã cedo ou no fim da tarde. A cobertura do solo (palha seca) reduz a evaporação e o calor na superfície.
- **Sombrite nas horas mais quentes:** um sombrite de 30 a 50% entre 11 h e 15 h, nos dias acima de 35 °C, já alivia muito.
- **Não encharque:** calor com substrato sempre molhado favorece podridão de raiz. Deixe a parte de cima secar entre as regas.
- **Cultive em várias plantas pequenas, não numa só grande:** se uma pegar fungo, as outras ficam.

## Estratégia por região

### Norte e Nordeste (0° a 13°S)

O dia fica entre cerca de 11 h 20 e 12 h 55 o ano todo. A luz não muda o suficiente para servir de calendário.

- **Automáticas** são a escolha natural: florescem pela idade, em cerca de 10 a 12 semanas desde a semente, independentemente da luz.
- **Fotoperiódicas** só fazem sentido se você vegetar a muda sob luz artificial (18 h por dia) até ela estar do tamanho que quer, e só então levá-la para fora. A floração começa quase imediatamente depois disso.
- **Quem manda é a chuva.** Planeje para que a floração não coincida com o pico da estação chuvosa da sua cidade, porque flor encharcada apodrece. O regime de chuvas varia muito dentro dessas regiões (Amazônia, litoral leste e semiárido têm calendários diferentes). Consulte as normais climatológicas do INMET para o seu município.
- **Calor:** acima de cerca de 35 °C a planta sofre. Regue cedo ou no fim da tarde, proteja as raízes do sol (vaso claro ou dentro de outro vaso) e use sombrite nos dias mais quentes.

### Centro-Oeste e interior do Sudeste (15° a 21°S)

O dia vai de cerca de 11 h em junho a 13 h em dezembro. O clima tem duas estações bem marcadas: seca de maio a setembro e chuvosa de outubro a março.

- **Automáticas na seca** (germinar entre abril e julho) é a combinação mais tranquila: céu limpo, pouca umidade e quase nenhum fungo. Em troca, você vai precisar irrigar.
- **Automáticas no verão** também funcionam, mas a floração cai no auge das chuvas. Escolha genéticas resistentes a fungos e prepare uma cobertura contra chuva.
- **Fotoperiódicas** vão para fora e começam a florir em poucas semanas. Vegete sob luz artificial antes ou aceite plantas menores.

### Litoral do Sudeste e Sul (22° a 34°S)

Aqui as fotoperiódicas viram uma opção real, principalmente no Paraná, em Santa Catarina e no Rio Grande do Sul.

- **Quando ir para fora:** setembro ou outubro, depois do risco de geada. O estudo de Santa Catarina (Camargo; Pandolfo; Bosco, 2024) encontrou o maior risco de geada em julho e concluiu que, a partir de meados de agosto, a geada deixa de limitar o plantio na maior parte do estado. Nas serras, confirme com o histórico local.
- **Como a planta se comporta:** ela vegeta enquanto os dias crescem até o solstício (21/dez). A floração começa à medida que os dias encurtam, de janeiro a fevereiro, conforme a latitude e a genética. Em Santa Catarina, o estudo estima a indução floral mais provável entre a segunda quinzena de fevereiro e março, considerando o crepúsculo.
- **Colheita:** março e abril. É a fase mais arriscada, porque coincide com chuva, noites mais frias e orvalho, o cenário clássico para podridão de flor.
- **Altitude:** acima de uns 700 m, o calor acumulado no verão pode não bastar para fechar o ciclo de variedades longas. Prefira genéticas mais rápidas ou automáticas.
- **No Rio, em São Paulo e em Belo Horizonte** o dia mais longo fica entre 13 h 20 e 13 h 35. As fotoperiódicas começam a florir cedo, então as estratégias do Centro-Oeste valem aqui também.

## Calendário de partida

Use como ponto de partida e ajuste ao clima da sua cidade.

| | Norte / Nordeste | Centro-Oeste / SE interior | SE litoral / Sul |
|---|---|---|---|
| **Automática, época principal** | Na estação mais seca local | Germinar abr–jul, colher jul–out | Germinar set–jan, colher dez–abr |
| **Automática, segunda rodada** | Possível o ano todo, fora do pico de chuva | Germinar ago–set (colheita já com chuvas) | Germinar fev (colher antes do frio) |
| **Fotoperiódica** | Só com vegetativo sob luz artificial | Vegetativo sob luz e floração na seca, ou plantas pequenas | Para fora em set–out, colher mar–abr |
| **Maior risco** | Calor e chuva concentrada | Fungos na floração de verão | Chuva e frio na colheita |

## Chuva, umidade e fungos

No Sul e no Sudeste, o verão brasileiro é quente e chuvoso justamente quando as flores estão se formando. Isso é o oposto do verão seco da Califórnia ou do Mediterrâneo, para onde muitos guias foram escritos. Algumas medidas ajudam:

- **Espaço e ventilação:** não encoste a planta em muros ou cercas que bloqueiam o vento. Retire folhas grandes que se sobrepõem no meio da copa (desfolha), porque é aí que a umidade fica presa.
- **Teto contra chuva:** uma cobertura de plástico transparente, aberta nas laterais, já reduz muito o risco de podridão de flor.
- **Depois da chuva:** sacuda os galhos para tirar o excesso de água e confira o miolo das flores mais grossas.
- **Genética:** prefira variedades descritas como resistentes a fungos e com flores menos compactas.
- **Colheita antecipada:** se a previsão indicar dias seguidos de chuva no fim do ciclo, colher uma semana antes é melhor do que perder a planta.

## Pragas mais comuns no Brasil

- **Lagartas:** comem as flores por dentro e abrem caminho para o fungo. O inseticida biológico à base de *Bacillus thuringiensis* (Bt) é o mais usado e é vendido em lojas agrícolas. Aplique antes da floração.
- **Formigas cortadeiras:** saúvas e quenquéns desfolham uma planta em uma noite. Encontre o formigueiro e use isca formicida específica, longe da planta.
- **Ácaros, pulgões e cochonilhas:** aparecem mais na seca e no calor. Sabão potássico ou óleo de neem resolvem no início. Evite aplicar nas flores.
- **Aliados:** joaninhas e larvas de crisopídeo comem pulgões e ácaros. Não os elimine.

## Checklist antes de plantar

- [ ] Sei a latitude da minha cidade e conferi a tabela de horas de luz
- [ ] Escolhi automática ou fotoperiódica de acordo com a minha região
- [ ] Conheço o calendário de chuvas local e a floração não cai no pior mês
- [ ] O lugar tem pelo menos 6 a 8 horas de sol direto por dia
- [ ] Não há luz artificial batendo na planta à noite
- [ ] Tenho um plano para chuva forte (cobertura ou vaso que dá para mover)
- [ ] Tenho Bt e isca para formigas antes de precisar deles
- [ ] Entendi a situação legal (veja o aviso acima)
