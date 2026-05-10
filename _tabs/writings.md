---
title: Writings
icon: fas fa-feather
order: 3
description: My own writings — published, in progress, and planned.
---

A catalogue of my own writings — works of fiction and personal essays, published or under way.

For texts about my work — recensions, interviews, news — see the post archive at the bottom of this page, or the dedicated catalogue inside each work.

{% comment %}
  Show one card per work — prefer EN, fall back to FR, then PT.
  Group by status (published / in-progress / planned).
{% endcomment %}

{% assign all_works = site.works %}
{% assign work_slugs = "" | split: "" %}
{% assign primary_works = "" | split: "" %}

{% for work in all_works %}
  {% assign segments = work.url | split: '/' %}
  {% assign slug = segments[2] %}
  {% unless work_slugs contains slug %}
    {% assign en_match = all_works | where_exp: "w", "w.url contains slug" | where: "lang", "en" | first %}
    {% assign fr_match = all_works | where_exp: "w", "w.url contains slug" | where: "lang", "fr" | first %}
    {% assign pt_match = all_works | where_exp: "w", "w.url contains slug" | where: "lang", "pt" | first %}
    {% assign chosen = en_match | default: fr_match | default: pt_match %}
    {% if chosen %}
      {% assign primary_works = primary_works | push: chosen %}
      {% assign work_slugs = work_slugs | push: slug %}
    {% endif %}
  {% endunless %}
{% endfor %}

{% assign published = primary_works | where: "status", "published" | sort: "year" | reverse %}
{% assign in_progress = primary_works | where: "status", "in-progress" | sort: "year" | reverse %}
{% assign planned = primary_works | where: "status", "planned" | sort: "year" | reverse %}

{% if published.size > 0 %}
## Published
{% include card-grid.html items=published %}
{% endif %}

{% if in_progress.size > 0 %}
## In progress
{% include card-grid.html items=in_progress %}
{% endif %}

{% if planned.size > 0 %}
## Planned
{% include card-grid.html items=planned %}
{% endif %}

---

## Recent posts about my work

{% assign work_posts = site.posts | where_exp: "p", "p.categories contains 'Writings'" | slice: 0, 5 %}

{% if work_posts.size > 0 %}
<ul class="writings-list">
{% for post in work_posts %}
  <li>
    <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a>
    <span class="post-date">— {{ post.date | date: "%d %b %Y" }}</span>
  </li>
{% endfor %}
</ul>
{% else %}
*No recent posts.*
{% endif %}

