---
layout: page
title: "Publications"
permalink: /publications/
---

{% assign pubs = site.publications | sort: "year" | reverse %}
{% assign journals = pubs | where: "type", "Journal" %}
{% assign conferences = pubs | where: "type", "Conference" %}

<p class="page-subtitle">Sorted by year and type. Click title to open paper PDF when available.</p>

{% if journals.size > 0 %}
<h2>Journal</h2>
{% assign current_year = "" %}
{% for p in journals %}
{% if p.year != current_year %}
{% assign current_year = p.year %}
<h3 class="year-group">{{ current_year }}</h3>
{% endif %}
{% assign title_href = p.url | relative_url %}
{% assign pdf_href = "" %}
{% if p.pdf %}
  {% if p.pdf contains '://' %}
    {% assign pdf_href = p.pdf %}
  {% else %}
    {% assign pdf_href = p.pdf | relative_url %}
  {% endif %}
  {% assign title_href = pdf_href %}
{% endif %}
<article class="pub-item">
  <a class="pub-title" href="{{ title_href }}" {% if p.pdf %}target="_blank" rel="noopener"{% endif %}><b>{{ p.title }}</b></a>
  {% if p.authors %}<div>{{ p.authors }}</div>{% endif %}
  <div>
    {% if p.venue %}<i>{{ p.venue }}</i>{% endif %}
    {% if p.year %}, {{ p.year }}{% endif %}
    {% if p.month %} ({{ p.month }}){% endif %}
  </div>
  <div class="pub-link-row">
    {% if p.doi %}<a href="https://doi.org/{{ p.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
    {% if p.pdf %} · <a href="{{ pdf_href }}" target="_blank" rel="noopener">PDF</a>{% endif %}
    {% if p.code %} · <a href="{{ p.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
    {% if p.url %} · <a href="{{ p.url | relative_url }}">Details</a>{% endif %}
  </div>
  {% if p.quick %}
  <details>
    <summary>Quick view</summary>
    {{ p.quick | markdownify }}
    {% if p.diagram %}
    {% include figure.html src=p.diagram alt="diagram" caption=p.diagram_caption %}
    {% endif %}
  </details>
  {% endif %}
</article>
{% endfor %}
{% endif %}

{% if conferences.size > 0 %}
<h2>Conference</h2>
{% assign current_year = "" %}
{% for p in conferences %}
{% if p.year != current_year %}
{% assign current_year = p.year %}
<h3 class="year-group">{{ current_year }}</h3>
{% endif %}
{% assign title_href = p.url | relative_url %}
{% assign pdf_href = "" %}
{% if p.pdf %}
  {% if p.pdf contains '://' %}
    {% assign pdf_href = p.pdf %}
  {% else %}
    {% assign pdf_href = p.pdf | relative_url %}
  {% endif %}
  {% assign title_href = pdf_href %}
{% endif %}
<article class="pub-item">
  <a class="pub-title" href="{{ title_href }}" {% if p.pdf %}target="_blank" rel="noopener"{% endif %}><b>{{ p.title }}</b></a>
  {% if p.authors %}<div>{{ p.authors }}</div>{% endif %}
  <div>
    {% if p.venue %}<i>{{ p.venue }}</i>{% endif %}
    {% if p.year %}, {{ p.year }}{% endif %}
    {% if p.month %} ({{ p.month }}){% endif %}
  </div>
  <div class="pub-link-row">
    {% if p.doi %}<a href="https://doi.org/{{ p.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
    {% if p.pdf %} · <a href="{{ pdf_href }}" target="_blank" rel="noopener">PDF</a>{% endif %}
    {% if p.code %} · <a href="{{ p.code }}" target="_blank" rel="noopener">Code</a>{% endif %}
    {% if p.url %} · <a href="{{ p.url | relative_url }}">Details</a>{% endif %}
  </div>
  {% if p.quick %}
  <details>
    <summary>Quick view</summary>
    {{ p.quick | markdownify }}
    {% if p.diagram %}
    {% include figure.html src=p.diagram alt="diagram" caption=p.diagram_caption %}
    {% endif %}
  </details>
  {% endif %}
</article>
{% endfor %}
{% endif %}
