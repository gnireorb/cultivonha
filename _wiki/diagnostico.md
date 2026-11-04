---
title: "Diagnóstico: o que a sua planta tem?"
titulo_curto: "Diagnóstico"
description: "Responda três perguntas (e, se quiser, o substrato) sobre o que você vê nas folhas e descubra as causas mais prováveis: deficiência, excesso de adubo, pH, rega, luz, calor ou praga, com fotos reais."
atualizado: '2026-11-04'
revisao: "Página criada em outubro de 2026, a partir das páginas Deficiências, Estresse, Rega, Pragas comuns e Fungos."
fontes_acesso: 2026-10-27
fontes:
  - abnt: "VEAZIE, P.; COCKSON, P.; SMITH, J. T.; SCHULKER, B.; JACKSON, B.; HICKS, K.; WHIPKER, B. Impact of substrate pH and micronutrient fertility rates on *Cannabis sativa*. **Agrosystems, Geosciences & Environment**, [S. l.], v. 8, n. 1, e70044, 2025. DOI: <https://doi.org/10.1002/agg2.70044>."
    nota: "Faixa de pH do substrato recomendada pelos autores e adotada pela wiki: 5,5 a 6,5. Em pH 3 e 4 a planta cresceu menos; em pH 7 houve menos raiz e as folhas tiveram cerca de metade do magnésio; em 6,5 a planta cresceu mais. Cânhamo rico em CBD, no vegetativo, em turfa com perlita."
  - abnt: "LLEWELLYN, D.; GOLEM, S.; JONES, A. M. P.; ZHENG, Y. Foliar symptomology, nutrient content, yield, and secondary metabolite variability of cannabis grown hydroponically with different single-element nutrient deficiencies. **Plants**, Basel, v. 12, n. 3, art. 422, 2023. DOI: <https://doi.org/10.3390/plants12030422>."
    nota: "Fotos de alta resolução da falta de N, P, K, Ca, Mg e S em plantas em floração (licença CC BY 4.0), recortadas das figuras originais."
  - abnt: "COCKSON, P.; LANDIS, H.; SMITH, T.; HICKS, K.; WHIPKER, B. E. Characterization of nutrient disorders of *Cannabis sativa*. **Applied Sciences**, Basel, v. 9, n. 20, art. 4432, 2019. DOI: <https://doi.org/10.3390/app9204432>."
    nota: "Sintomas de cada deficiência e fotos dos micronutrientes e dos excessos (licença CC BY 4.0), recortadas das figuras originais."
  - abnt: "RUIZ DIAZ, D. A.; MARTIN, K. L.; MENGEL, D. B. **Diagnosing nutrient deficiencies in the field**. Manhattan: Kansas State University, 2011. (MF3028). Disponível em: <https://bookstore.ksre.ksu.edu/pubs/MF3028.pdf>."
    nota: "Nutrientes móveis e imóveis e onde a deficiência aparece primeiro."
---

Responda o que você vê na planta (e, se quiser, o substrato, que muda bastante as chances) e o diagnóstico mostra as **causas mais prováveis**, da mais para a menos provável, com fotos reais, o que fazer e como confirmar. Todas as fotos são de plantas de verdade, enviadas pela comunidade ou de estudos científicos; nenhuma foi gerada por inteligência artificial.

Termos sublinhados com pontinhos, como **folíolo** e **drenagem**, abrem a explicação ao tocar. O diagnóstico funciona no seu navegador e não guarda nem envia nada.

{% include diagnostico-atalho.html titulo="Comece aqui: onde o problema começou?" %}

## Antes de começar

Na maioria dos casos que aparecem no sub, o problema **não é falta de adubo**. Confira estes quatro pontos, porque cada um imita uma deficiência:

1. **pH** da rega e do que sai pelo fundo do vaso. Veja [pH e EC]({{ '/ph-ec/' | relative_url }}).
2. **Rega:** o substrato está sempre molhado, ou secando demais?
3. **Luz e calor:** o problema está só no topo, perto da lâmpada?
4. **Pragas:** olhe embaixo das folhas com uma lupa.

Para olhar a planta, use **luz branca** (a lanterna do celular ou a luz do dia). Com a luminária roxa ou amarelada acesa, as cores enganam.

<div id="diagnostico" class="diagnostico" data-base="{{ '/' | relative_url }}" data-reddit="{{ site.reddit_url }}">
  <noscript><p>O diagnóstico precisa de JavaScript. Sem ele, use a tabela da página <a href="{{ '/deficiencias/' | relative_url }}#sintoma-por-nutriente">Deficiências</a>.</p></noscript>
</div>

<script type="application/json" id="diagnostico-dados">{{ site.data.diagnostico | jsonify }}</script>
<script type="application/json" id="diagnostico-casos">{{ site.data.casos_diagnostico | jsonify }}</script>
<script type="application/json" id="diagnostico-glossario">{{ site.data.glossario.termos | where_exp: "t", "t.diagnostico" | jsonify }}</script>
<script src="{{ '/assets/js/diagnostico.js' | relative_url }}?v={{ site.time | date: '%s' }}" defer></script>

## Calculadora de dose

Quando o resultado for falta de potássio, de magnésio ou de cálcio, o botão **Calcular a dose** põe o produto aqui. Diga quantos litros de água vai preparar e veja quanto pesar.

{% include calculadora-dose.html %}

## Ainda em dúvida?

- Sem análise de folha, os micronutrientes (ferro, manganês, zinco, cobre e boro) são difíceis de separar. Na prática, **acerte o pH e use um adubo completo**.
- **Mude uma coisa de cada vez** e espere alguns dias. O sinal de que deu certo é a **folha nova** sair saudável: a folha danificada não volta a ficar verde.
- Poste no sub com as informações pedidas em [Pragas e problemas]({{ '/pragasproblemas/' | relative_url }}): fotos com luz branca, fase da planta, substrato, adubo e dose, pH da rega e há quanto tempo o sintoma apareceu.

As fotos marcadas como "estudo" são de dois trabalhos com plantas cultivadas sem cada nutriente, em ambiente controlado, sob licença [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): Llewellyn *et al.* (2023), para nitrogênio, fósforo, potássio, cálcio, magnésio e enxofre, e Cockson *et al.* (2019), para os micronutrientes e os excessos. As do segundo estudo têm resolução baixa, porque a revista só publicou as figuras pequenas. As outras são de membros do r/Cultivonha, com o crédito em cada uma. Os **casos do r/Cultivonha** que aparecem em cada resultado são os cards das outras páginas da wiki, com o diagnóstico dado pela comunidade. Tem uma foto boa de algum desses sintomas? Mande no sub: ela pode virar um caso.
