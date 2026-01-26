---
layout: default
title: Episodes
permalink: /episodes/
---

<ul>
  {% assign eps = site.episodes | sort: "date" | reverse %}
  {% for ep in eps %}
    <li>
      <a href="{{ ep.url | relative_url }}">{{ ep.title }}</a>
      — {{ ep.date | date: "%b %-d, %Y" }}
    </li>
  {% endfor %}
</ul>
