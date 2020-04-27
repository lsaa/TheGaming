---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

<p style="text-align:left;">
    <span style="float:right;">
        {{ page.author }}
    </span>
    <h1>{{ page.title }}</h1>
</p>


{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
