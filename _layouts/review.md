---
layout: default
permalink: /post/:title
---

{{ page.date | date: "%-d %B %Y" }}

<div style="text-align:left; margin-bottom: -18px;">
    <h1 style="display: inline-block;">{{ page.title }}</h1>
    <span style="float:right; position: relative; bottom: -10px;">
        by {{ page.author }}
    </span>
</div>
<hr>
<div>
  <p style="color: #6e6e6e;">
    <img style="width: 64px; float: left; padding: 10px; padding-left: 0px; padding-top: 0px" src="{{site.baseurl}}{{page.g-img-cover}}">
    <span style="vertical-align: top;">{{page.title}} ({{page.g-main-year}})</span>
    <br>
    <span style="vertical-align: top" class="ban2">{{page.g-dev}}</span>
    <br>
    <span style="vertical-align: top" class="ban2">{{page.g-platforms[0]}}</span>
  </p>
</div>
{{content}}

{% if page.tags %}
  <small>tags: <em>{{ page.tags | join: "</em> - <em>" }}</em></small>
{% endif %}
