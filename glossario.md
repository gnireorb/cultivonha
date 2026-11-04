---
layout: doc
title: Glossário
description: Termos de cultivo em inglês e como os traduzimos em todo o site.
permalink: /glossario/
---

Este é o mesmo arquivo (`_data/glossario.yml`) que o script de tradução usa, então o site e as traduções sempre falam a mesma língua.

{% assign termos = site.data.glossario.termos | sort: "en" %}
<dl class="glossario">
{% for t in termos %}
  <div class="termo" id="{{ t.en | slugify }}">
    <dt><strong>{{ t.pt }}</strong> <span class="en">{{ t.en }}</span></dt>
    {% if t.definicao %}<dd>{{ t.definicao }}</dd>{% endif %}
    {% if t.manter_original %}<dd class="nota">Costuma ficar em inglês no meio cultivador; usamos o termo original com explicação na primeira menção.</dd>{% endif %}
  </div>
{% endfor %}
</dl>
