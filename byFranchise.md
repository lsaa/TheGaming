---
permalink: /reviews-franchise/
---

<div>
{% assign reviews = site.categories.review | sort: "g-franchise", "g-franchise-order", "g-main-year" %}
{% for post in reviews %}
    {% capture franchise %}{{ post.g-franchise }}{% endcapture %}
    {% capture next_francise %}{{ post.previous.g-franchise }}{% endcapture %}

    {% if forloop.first %}
    <h2 id="{{ franchise }}-ref">{{ franchise }}</h2>
    <ul>
    {% endif %}

    <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.date | date: "%Y-%m-%-d" }} - {{ post.title }}</a></li>

    {% if forloop.last %}
    </ul>
    {% else %}
        {% if franchise != next_franchise %}
        </ul>
        <h2 id="{{ next_franchise }}-ref">{{ next_franchise }}</h2>
        <ul>
        {% endif %}
    {% endif %}
{% endfor %}
</div>
