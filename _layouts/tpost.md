---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

# {{ page.title }}

{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
