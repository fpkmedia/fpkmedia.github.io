---
layout: default
title: Home
---

Welcome to **{{ site.title }}**.

{{ site.description }}

## Latest episodes
{% assign eps = site.episodes | sort: "date" | reverse %}
<ul>
  {% for ep in eps limit:5 %}
    <li><a href="{{ ep.url | relative_url }}">{{ ep.title }}</a> — {{ ep.date | date: "%b %-d, %Y" }}</li>
  {% endfor %}
</ul>
