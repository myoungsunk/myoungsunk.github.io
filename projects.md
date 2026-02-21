---
layout: page
title: "Projects"
permalink: /projects/
---

{% assign ps = site.projects | sort: "year_end" | reverse %}

{% for pr in ps %}
<article class="project-card">
  <h2><a href="{{ pr.url | relative_url }}">{{ pr.title }}</a></h2>
  {% if pr.period %}<div><b>Period:</b> {{ pr.period }}</div>{% endif %}
  {% if pr.summary %}<p>{{ pr.summary }}</p>{% endif %}
  {% if pr.keywords %}<div><b>Keywords:</b> {{ pr.keywords | join: ", " }}</div>{% endif %}
  <div class="pub-link-row"><a href="{{ pr.url | relative_url }}">Details</a></div>
</article>
{% endfor %}
