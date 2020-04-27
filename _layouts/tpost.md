---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

# {{ page.title }}

---

*test*

{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
