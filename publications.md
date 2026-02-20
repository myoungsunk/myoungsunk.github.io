---
layout: single
title: "Publications"
permalink: /publications/
---

This page is generated from `_data/publications.yml`.

## Journal articles
{% assign journals = site.data.publications | where: "type", "Journal" | sort: "year" | reverse %}
{% for p in journals %}
- **{{ p.title }}**  
  {{ p.authors }}  
  *{{ p.venue }}*, {{ p.year }}{% if p.month %} ({{ p.month }}){% endif %}.  
  {% if p.doi %}DOI: [{{ p.doi }}]({{ p.links.doi }}){% endif %}
  {% if p.links.paper %} · [paper]({{ p.links.paper }}){% endif %}
  {% if p.links.preprint %} · [preprint]({{ p.links.preprint }}){% endif %}
{% endfor %}

## Conference papers
{% assign confs = site.data.publications | where: "type", "Conference" | sort: "year" | reverse %}
{% for p in confs %}
- **{{ p.title }}**  
  {{ p.authors }}  
  *{{ p.venue }}*, {{ p.year }}{% if p.month %} ({{ p.month }}){% endif %}.  
  {% if p.doi %}DOI: [{{ p.doi }}]({{ p.links.doi }}){% endif %}
  {% if p.links.paper %} · [paper]({{ p.links.paper }}){% endif %}
{% endfor %}
