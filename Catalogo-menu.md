---
layout: page
title: Catálogo de Plantas
permalink: /catalogo-menu/
nav_order: 3
---

## Catálogo del Jardín Botánico del Colegio

Aquí puedes explorar todas las especies que tenemos, clasificadas por tipo.

{% comment %} 
   Asignamos la colección a una variable para ordenarla alfabéticamente por título 
{% endcomment %}
{% assign plantas_ordenadas = site.catalogo | sort: "title" %}

{% comment %} 
   Función de ayuda para renderizar cada lista
{% endcomment %}
{% assign tipos_de_planta = "arbol|Árboles,arbusto|Arbustos,floral|Florales,suculenta|Suculentas,otras|Otras" | split: "," %}

{% for tipo in tipos_de_planta %}
    {% assign key = tipo | split: "|" | first %}
    {% assign title = tipo | split: "|" | last %}
    
    {% assign plantas_filtradas = plantas_ordenadas | where: "tipo_planta", key %}

    {% if plantas_filtradas.size > 0 %}
        <h2 id="{{ key }}">{{ title }} ({{ plantas_filtradas.size }})</h2>
        <ul class="catalogo-list">
        {% for planta in plantas_filtradas %}
            <li>
                <a href="{{ planta.url | relative_url }}">
                    **{{ planta.title }}**
                    {% if planta.nombre_cientifico %} 
                        ({{ planta.nombre_cientifico }})
                    {% endif %}
                </a>
            </li>
        {% endfor %}
        </ul>
        <hr>
    {% endif %}

{% endfor %}