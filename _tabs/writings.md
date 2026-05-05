---
icon: fas fa-feather
order: 1
description: Escritos e textos publicados.
---

{% assign writings = site.posts | where_exp: "p", "p.categories contains 'Writings'" %}

{% if writings.size == 0 %} *Ainda sem escritos publicados.* {% else %}

<ul class="writings-list">
{% for post in writings %}
 <li>
 <a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a>
 <span class="post-date">— {{ post.date | date: "%d %b %Y" }}</span>
 {% if post.excerpt %}
 <p>{{ post.excerpt | strip_html | truncate: 220 }}</p>
 {% endif %}
 </li>
{% endfor %}
</ul>
{% endif %}
