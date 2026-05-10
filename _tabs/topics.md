---
title: Topics
icon: fas fa-compass
order: 4
description: Topics of interest — notes, readings, and references on consciousness, AI, NDEs, UFOs, and other questions.
---

A small map of subjects I keep returning to. Each topic is a starting point — a brief overview, a set of readings, a few people worth following — with branches into more specific questions when the material calls for it.

The site is a work in progress, and these pages will grow as I do.

{% comment %}
  Show only one card per topic — prefer EN, fall back to FR, then PT.
{% endcomment %}

{% assign all_landings = site.topics | where_exp: "t", "t.is_landing == true" %}
{% assign topic_slugs = "" | split: "" %}
{% assign primary_landings = "" | split: "" %}

{% for landing in all_landings %}
  {% assign segments = landing.url | split: '/' %}
  {% assign slug = segments[2] %}
  {% unless topic_slugs contains slug %}
    {% assign en_match = all_landings | where_exp: "t", "t.url contains slug" | where: "lang", "en" | first %}
    {% assign fr_match = all_landings | where_exp: "t", "t.url contains slug" | where: "lang", "fr" | first %}
    {% assign pt_match = all_landings | where_exp: "t", "t.url contains slug" | where: "lang", "pt" | first %}
    {% assign chosen = en_match | default: fr_match | default: pt_match %}
    {% if chosen %}
      {% assign primary_landings = primary_landings | push: chosen %}
      {% assign topic_slugs = topic_slugs | push: slug %}
    {% endif %}
  {% endunless %}
{% endfor %}

{% assign primary_landings = primary_landings | sort: "order" %}

{% include card-grid.html items=primary_landings %}

