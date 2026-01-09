---
layout: page
title: Catálogo de Plantas
permalink: /catalogo-menu/
nav-include: true
nav-order: 3
---

## Catálogo del Jardín Botánico del Colegio

Aquí puedes explorar todas las especies que tenemos, clasificadas por tipo.
{% assign plantas_coleccion = site.catalogo | sort: "title" %}

### Árboles

<ul class="plant-list">
{% for planta in plantas_coleccion %}
  {% if planta.tipo_planta == 'arbol' %}
    <li>
      <a href="{{ planta.url | relative_url }}">
        <strong>{{ planta.title }}</strong>
        <span class="nombre-cientifico">(<em>{{ planta.nombre_cientifico }}</em>)</span>
      </a>
    </li>
  {% endif %}
{% endfor %}
</ul>
