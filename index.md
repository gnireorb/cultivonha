---
title: r/Cultivonha
description: A wiki da comunidade brasileira de cultivo caseiro, adaptada ao clima e às leis do Brasil.
classe_body: inicio
---
{%- assign todas = site.pages | concat: site.wiki -%}
<main id="conteudo" class="inicio-principal">
  <section class="abertura">
    {%- assign hoje = site.time | date: "%Y-%m-%d" -%}
    {% if site.tema_politico_ate and hoje <= site.tema_politico_ate %}<p class="abertura-chamada" data-tema-politico>Cultivar é um ato político</p>{% endif %}
    <h1 class="abertura-titulo">r/<span>Culti</span>vonha</h1>
    {% if site.tema_politico_ate and hoje <= site.tema_politico_ate %}<p class="selo" aria-hidden="true" data-tema-politico>Democracia se planta todo dia</p>{% endif %}
    <p class="abertura-texto">A wiki de quem cultiva em casa no Brasil. Escrita pela comunidade, com graus Celsius, estações do hemisfério sul e produtos que se encontram por aqui.</p>
    <div class="abertura-busca" id="busca-inicio"></div>
  </section>

  {% include diagnostico-atalho.html %}

  <section class="espectro" aria-labelledby="titulo-espectro">
    <h2 id="titulo-espectro">Assuntos</h2>
    <ul class="espectro-lista">
      {% for s in site.data.navegacao.secoes %}
      {%- assign primeira = todas | where: "url", s.paginas[0] | first -%}
      <li class="espectro-item cor-{{ s.cor }}">
        <a href="{{ '/indice/' | relative_url }}#{{ s.id }}">
          <strong>{{ s.nome }}</strong>
          <span>{% for u in s.paginas limit: 3 %}{%- assign p = todas | where: "url", u | first -%}{% if p %}{{ p.titulo_curto | default: p.title }}{% unless forloop.last %}, {% endunless %}{% endif %}{% endfor %}{% if s.paginas.size > 3 %} e mais{% endif %}</span>
        </a>
      </li>
      {% endfor %}
    </ul>
  </section>

  <div class="inicio-colunas">
    <section class="comecar">
      <h2>Para o primeiro cultivo</h2>
      <ol class="trilha-leitura">
        {% assign trilha = "/primeiro-cultivo/,/estufabasica/,/sementes/,/germinacao/,/rega/,/colheita/" | split: "," %}
        {% for u in trilha %}{%- assign p = todas | where: "url", u | first -%}
        {% if p %}<li><a href="{{ p.url | relative_url }}">{{ p.title }}</a><span>{{ p.description }}</span></li>{% endif %}
        {% endfor %}
      </ol>
    </section>

    <aside class="inicio-lateral">
      <section class="convite">
        <h2>Ficou com dúvida?</h2>
        <p>Poste no <a href="{{ site.reddit_url }}" rel="noopener">r/{{ site.subreddit }}</a> com fotos e os dados do seu cultivo: substrato, fertilizante, luz, temperatura, umidade e pH. A página de <a href="{{ '/pragasproblemas/' | relative_url }}">pragas e problemas</a> explica o que incluir.</p>
      </section>
    </aside>
  </div>
</main>
