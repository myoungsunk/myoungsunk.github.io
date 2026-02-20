---
layout: single
title: "Myoungsun Kim"
permalink: /
---

POSTECH Electrical Engineering Ph.D. student.  
Research interests: **wireless localization**, **Direction-of-Arrival (DoA)**, **RSS/RSSD-based sensing**, and RF/antenna systems that enable robust positioning in indoor and multipath environments.

Links:
- Google Scholar: https://scholar.google.com/citations?user=fD7i2qgAAAAJ&hl=ko&oi=ao
- GitHub: (TODO)
- Email: (TODO)

## Research focus
I work on localization problems where **hardware constraints** (resource-limited tags, limited field-of-view, calibration errors) and **RF propagation effects** (multipath, shadowing) directly impact estimation accuracy.  
My recent work spans:
- **Decentralized indoor localization** using RSSD-based DoA and tag/system design
- **Calibration/compensation** methods to improve DoA accuracy under practical constraints
- **RF front-end / antenna / measurement systems** supporting wireless communication & sensing

## Featured publications
{% assign featured_pubs = site.data.publications | where: "featured", true | sort: "year" | reverse %}
{% for p in featured_pubs %}
- **{{ p.title }}**  
  {{ p.authors }}  
  *{{ p.venue }}*, {{ p.year }}{% if p.month %} ({{ p.month }}){% endif %}.  
  {% if p.doi %}DOI: [{{ p.doi }}]({{ p.links.doi }}){% endif %}{% if p.links.paper %} · [paper]({{ p.links.paper }}){% endif %}
{% endfor %}

## Featured projects
{% assign featured_projects = site.data.projects | where: "featured", true | sort: "year_end" | reverse %}
{% for pr in featured_projects %}
- **{{ pr.title }}** ({{ pr.period }})  
  {{ pr.summary }}  
  Keywords: {{ pr.keywords | join: ", " }}  
  {% if pr.links.paper %}[related paper]({{ pr.links.paper }}){% endif %}
{% endfor %}

## Contact
If you’d like to discuss collaboration or opportunities, please reach out:
- Email: (TODO)
