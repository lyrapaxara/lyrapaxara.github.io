---
title: Flores de Jasmim
lang: pt
permalink: /works/flores-de-jasmim/
status: published
genre: romance
year: 2011
language_original: Portuguese
publisher: Livraria Orfeu, Bruxelas
isbn: 
buy_url: https://www.livrariaorfeu.com/edicoes-orfeu
cover: /assets/img/posts/flores-de-jasmim-capa.png
description: Romance ambientado na Madeira do final dos anos sessenta, ao redor da vida no seminário e do despertar de uma sociedade insular em vésperas de transformação.
showcase_url: /flores-de-jasmim/
order: 1
---

{% include lang-switcher-collection.html %}

> «*Flores de Jasmim* é uma ficção em que, tal como no universo onírico, personagens imaginárias se entremeiam com reminiscências de outrora para compor o cenário do romance.»
>
> — João Gabriel Correia

## Sobre

Romance, edição da [Livraria Orfeu](https://www.livrariaorfeu.com), Bruxelas, 2011. Apresentado publicamente em três eventos em Maio de 2011: Bruxelas (17), Santana (20), Funchal (28).

Ambientado na Madeira do final dos anos sessenta, *Flores de Jasmim* atravessa o microcosmos do seminário e o despertar de uma sociedade insular em vésperas de transformação. Personagens, lugares e memórias entrelaçam-se na fronteira ténue entre o vivido e o imaginado.

## Para encomendar

> 📖 [**Encomendar na Livraria Orfeu**](https://www.livrariaorfeu.com/edicoes-orfeu){:target="_blank"}

## Recensões e referências

{% if site.data.recensoes and site.data.recensoes.size > 0 %}
{%- assign type_labels = "critica:Crítica,noticia:Notícia,entrevista:Entrevista,mencao:Menção" | split: "," -%}
{%- assign sorted = site.data.recensoes | sort: "date" | reverse -%}

<ul class="referencias-list">
{%- for ref in sorted %}
  <li class="referencia-item">

    {%- assign type_label = ref.type -%}
    {%- for pair in type_labels -%}
      {%- assign parts = pair | split: ":" -%}
      {%- if parts[0] == ref.type -%}{%- assign type_label = parts[1] -%}{%- endif -%}
    {%- endfor -%}
    <span class="referencia-tipo referencia-tipo-{{ ref.type }}">{{ type_label }}</span>

    <span class="referencia-title">
      {%- if ref.url -%}
        {%- assign is_external = ref.url | slice: 0, 4 -%}
        {%- if is_external == "http" -%}
          <a href="{{ ref.url }}" target="_blank" rel="noopener">{{ ref.title }}</a>
        {%- else -%}
          <a href="{{ ref.url | relative_url }}">{{ ref.title }}</a>
        {%- endif -%}
      {%- else -%}
        {{ ref.title }}
      {%- endif -%}
    </span>

    <span class="referencia-meta">
      {%- if ref.author %}{{ ref.author }}{% endif -%}
      {%- if ref.author and ref.source %} · {% endif -%}
      {%- if ref.source -%}<em>{{ ref.source }}</em>{%- endif -%}
      {%- if ref.date %} · {{ ref.date | date: "%d %b %Y" }}{% endif -%}
    </span>

    {%- if ref.original_url %}
      <span class="referencia-extra">
        <a href="{{ ref.original_url }}" target="_blank" rel="noopener" title="Versão original">↗ original</a>
      </span>
    {%- endif -%}

  </li>
{%- endfor %}
</ul>
{%- endif %}

---

*Para a apresentação completa do livro, ver a [página dedicada](/flores-de-jasmim/).*

