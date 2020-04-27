---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

<p style="text-align:left;">
    <span style="float:right;">
        {{ page.author }}
    </span>
    <h1 style="display: inline-block;">{{ page.title }}</h1>
</p>
<hr>
{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
