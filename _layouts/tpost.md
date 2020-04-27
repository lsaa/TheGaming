---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

<p style="text-align:left;">
    <h1>{{ page.title }}</h1>
    <span style="float:right;">
        {{ page.author }}
    </span>
</p>


{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
