---
layout: default
title: Guía de Botánica
permalink: /botanica-menu/
nav_order: 1
---

# 🌿 Guía Completa de Conceptos de Botánica

Haz clic en un tema a continuación para obtener más información.

<ul class="concept-list">
{% assign sorted_botanica = site.botanica | sort: "concept_id" %}
{% for concepto in sorted_botanica %}
  <li>
    <a href="{{ concepto.url | relative_url }}">{{ concepto.title }}</a>
  </li>
{% endfor %}
</ul>