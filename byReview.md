---
permalink: /reviews/
---

{% assign fr = "" | split: ',' %}

<div>
{% assign reviews = site.posts | sort: "g-main-year" %}
{% assign reviews = reviews | sort: "g-franchise-order" %}
{% assign reviews = reviews | sort: "g-franchise" %}
{% for post in reviews %}
    {% assign fr = fr | push: post.date | date: "%Y" %}
{% endfor %}

<table>
{% assign fr = fr | uniq %}
{% assign frCount = "" | split: ',' %}

{% for franchise in fr %}
    {% if franchise %}
        {% assign counter = 0 %}
        {% for post in reviews %}
            {% if post.date | date: "%Y" == franchise and post.date | date: "%Y" %}
                {% assign counter = counter | plus: 1 %}
            {% endif %}
        {% endfor %}
        {% assign frCount = frCount | push: counter %}
    {% endif %}
{% endfor %}


{% assign franchiseCC = -1 %}
{% for franchise in fr %}
    {% for post in reviews %}
        {% if post.date | date: "%Y" == franchise and post.date | date: "%Y" %}
            {% if post.date | date: "%Y" == 1 %}
                {% assign franchiseCC = franchiseCC | plus: 1 %}
                <tr>
                    <td rowspan="{{frCount[franchiseCC]}}" style="vertical-align: top">{{franchise}}</td>
                    <td><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></td>
                </tr>
            {% else %}
                <tr>
                    <td><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></td>
                </tr>
            {% endif %}
        {% endif %}
    {% endfor %}
{% endfor %}
</table>
</div>

