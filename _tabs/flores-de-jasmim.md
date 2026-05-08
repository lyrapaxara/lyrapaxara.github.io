---
title: «Flores de Jasmim»
icon: fas fa-book
order: 2
description: Romance de João Gabriel Correia. Edição da Livraria Orfeu, Bruxelas.
---

![Capa do romance «Flores de Jasmim», de João Gabriel Correia](/assets/img/posts/flores-de-jasmim-capa.png){: width="220" .right }

> «*Flores de Jasmim* é uma ficção em que, tal como no universo onírico, personagens imaginárias se entremeiam com reminiscências de outrora para compor o cenário do romance. Que o leitor, ao acordar da narrativa, sinta simplesmente o prazer do divertimento!»
>
> — João Gabriel Correia

## Sobre o romance

Ambientado na Madeira do final dos anos sessenta, *Flores de Jasmim* atravessa o microcosmos do seminário e o despertar de uma sociedade insular em vésperas de transformação. Personagens, lugares e memórias entrelaçam-se na fronteira ténue entre o vivido e o imaginado.

## Edição

![Livraria Orfeu — Bruxelas](/assets/img/orfeu-logo.png){: width="90" .left }

O romance é uma edição da [**Livraria Orfeu**](https://www.livrariaorfeu.com), em Bruxelas — casa de referência para a literatura portuguesa fora de portas, fundada e dirigida por Joaquim Pinto da Silva.

A apresentação pública do livro decorreu na própria livraria a 17 de Maio de 2011, pelo Dr. Joaquim Silva Rodrigues.

## Como encomendar

O livro pode ser encomendado em linha directamente no catálogo Orfeu:

> 📖 [**Encomendar «Flores de Jasmim» na Livraria Orfeu**](https://www.livrariaorfeu.com/edicoes-orfeu){:target="_blank"}

Para questões directas —  dedicatórias, ou qualquer outro contacto sobre o livro —, [escreve-me](mailto:contact@lyrapaxara.eu).

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
{%- else %}
*Ainda sem recensões registadas.*
{%- endif %}
