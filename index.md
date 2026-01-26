---
layout: default
title: Home
---

## Latest episodes

{% assign eps = site.episodes | sort: "date" | reverse %}
<div class="grid">
  {% for ep in eps limit:6 %}
    <div class="card">
      <a href="{{ ep.url | relative_url }}"><h2 class="card-title">{{ ep.title }}</h2></a>
      <div class="meta">{{ ep.date | date: "%b %-d, %Y" }}{% if ep.duration %} · {{ ep.duration }}{% endif %}</div>
      {% if ep.summary %}<div class="summary">{{ ep.summary }}</div>{% endif %}
      <div class="meta" style="margin-top:10px;">
        <a href="{{ ep.url | relative_url }}">Open episode →</a>
      </div>
    </div>
  {% endfor %}
</div>

<div style="margin-top:14px;">
  <a class="btn" href="{{ '/episodes/' | relative_url }}">View all episodes</a>
</div>
