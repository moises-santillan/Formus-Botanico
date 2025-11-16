---
layout: page
title: Catálogo de Plantas
permalink: /Catalogo-menu/
---

## Catálogo del Jardín Botánico del Colegio

Aquí puedes explorar todas las especies que tenemos, clasificadas por tipo.

<ul class="plant-list">
{% assign plantas_coleccion = site.catalogo | sort: "tipo_planta" %}
{% for planta in plantas_coleccion %}
  <li>
    <a href="{{ planta.url | relative_url }}">
      **{{ planta.title }}**,
      <span class="nombre-cientifico">({{ planta.nombre_cientifico }})</span>,
      <span class="tipo-planta">Tipo: {{ planta.tipo_planta }}</span>
    </a>
  </li>
{% endfor %}
</ul>
