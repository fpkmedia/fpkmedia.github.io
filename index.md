---
layout: default
title: Home
---

{% assign eps = site.episodes | sort: "date" | reverse %}

## Latest episodes

<div class="grid">
  {% for ep in eps limit:5 %}
    <article class="card">
      <div class="ep-head">
        <div>
          <h2 class="card-title"><a href="{{ ep.url | relative_url }}">{{ ep.title }}</a></h2>
          <div class="meta">
            {{ ep.date | date: "%B %-d, %Y" }}
            {% if ep.duration %} · {{ ep.duration }}{% endif %}
            {% if ep.episode %} · Episode {{ ep.episode }}{% endif %}
          </div>
        </div>
        <div class="ep-actions">
          <a class="btn ghost" href="{{ ep.url | relative_url }}">View</a>
        </div>
      </div>

      {% if ep.audio_url %}
        <audio controls preload="none">
          <source src="{{ ep.audio_url }}" type="audio/mpeg">
        </audio>
      {% endif %}

      {% if ep.summary %}
        <div class="summary">{{ ep.summary }}</div>
      {% endif %}
    </article>
  {% endfor %}
</div>

<div style="margin-top:14px;">
  <a class="btn" href="{{ '/episodes/' | relative_url }}">Browse all episodes</a>
  <a class="btn ghost" href="{{ '/subscribe/' | relative_url }}">Subscribe</a>
</div>
