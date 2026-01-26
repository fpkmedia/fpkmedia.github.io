---
layout: default
title: Episodes
permalink: /episodes/
---

{% assign eps = site.episodes | sort: "date" | reverse %}
<div class="grid">
  {% for ep in eps %}
    <div class="card">
      <a href="{{ ep.url | relative_url }}"><h2 class="card-title">{{ ep.title }}</h2></a>
      <div class="meta">{{ ep.date | date: "%b %-d, %Y" }}{% if ep.duration %} · {{ ep.duration }}{% endif %}{% if ep.episode %} · Episode {{ ep.episode }}{% endif %}</div>
      {% if ep.summary %}<div class="summary">{{ ep.summary }}</div>{% endif %}
    </div>
  {% endfor %}
</div>
