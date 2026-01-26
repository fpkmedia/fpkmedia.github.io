---
layout: default
title: Episodes
permalink: /episodes/
---

{% assign eps = site.episodes | sort: "date" | reverse %}
<ul class="list">
  {% for ep in eps %}
    <li class="card">
      <a href="{{ ep.url | relative_url }}"><strong>{{ ep.title }}</strong></a>
      <div class="meta">{{ ep.date | date: "%b %-d, %Y" }}{% if ep.duration %} · {{ ep.duration }}{% endif %}</div>
      {% if ep.summary %}<div>{{ ep.summary }}</div>{% endif %}
    </li>
  {% endfor %}
</ul>
