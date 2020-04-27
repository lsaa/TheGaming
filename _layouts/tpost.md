---
layout: default
---

{{ page.date | date: "%-d %B %Y" }}

<div style="text-align:left; margin-bottom: -5;">
    <span style="float:right;">
        {{ page.author }}
    </span>
    <h1 style="display: inline-block;">{{ page.title }}</h1>
</div>
<hr>
{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
