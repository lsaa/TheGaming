---
permalink: /reviews-year/
---

<div>
{% for post in site.categories.review reversed %}
    {% capture this_year %}{{ post.g-main-year }}{% endcapture %}
    {% capture next_year %}{{ post.previous.g-main-year }}{% endcapture %}

    {% if forloop.first %}
    <h2 id="{{ this_year }}-ref">{{this_year}}</h2>
    <ul>
    {% endif %}

    <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.date | date: "%Y-%m-%-d" }} - {{ post.title }}</a></li>

    {% if forloop.last %}
    </ul>
    {% else %}
        {% if this_year != next_year %}
        </ul>
        <h2 id="{{ next_year }}-ref">{{next_year}}</h2>
        <ul>
        {% endif %}
    {% endif %}
{% endfor %}
</div>
