---
layout: page
title: Catálogo de Plantas
permalink: /Catalogo-menu/
---

## Catálogo del Jardín Botánico del Colegio

Aquí puedes explorar todas las especies que tenemos, clasificadas por tipo.

{% assign sorted_pantas = site.catalogo | sort: "tipo_planta" %}
{% for planta in sorted_plantas %}
  <li>
    <a href="{{ planta.url | relative_url }}">{{ planta.title }}, ({{ planta.tipo }})</a>
  </li>
{% endfor %}
</ul>