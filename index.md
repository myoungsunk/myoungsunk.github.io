---
layout: default
title: "Myoungsun Kim"
permalink: /
---

Ph.D. student in Electrical Engineering at POSTECH (advisor: Prof. Wonbin Hong).  
Research interests: **wireless indoor localization**, **Direction-of-Arrival (DoA)**, **RSS/RSSD-based sensing**, and **RF/antenna measurement systems**.

Links:
- Google Scholar: [Profile](https://scholar.google.com/citations?user=fD7i2qgAAAAJ&hl=ko&oi=ao)
- GitHub: [myoungsunk](https://github.com/myoungsunk)
- CV (Web): [Open CV]({{ '/assets/files/cv/CV_Myoungsunkim_25.05_ticra.html' | relative_url }})
- CV (DOCX): [Download DOCX]({{ '/assets/files/cv/CV_Myoungsunkim_25.05_ticra.docx' | relative_url }})
- CV (PDF): [Open PDF]({{ '/assets/files/curriculum_vitae.pdf' | relative_url }})
- Email: [myoungsunkim@postech.ac.kr](mailto:myoungsunkim@postech.ac.kr)

## Research focus
I work on localization problems where **hardware constraints** (resource-limited tags, limited field-of-view, calibration errors) and **RF propagation effects** (multipath, shadowing) directly impact estimation accuracy.  
My recent work spans:
- **Decentralized indoor localization** using RSSD-based DoA and tag/system design
- **Calibration/compensation** methods to improve DoA accuracy under practical constraints
- **RF front-end / antenna / measurement systems** supporting wireless communication & sensing

## Education
- **Pohang University of Science and Technology (POSTECH)**, Ph.D. Student in Electrical Engineering (Mar. 2023 - Present)
- **Pohang University of Science and Technology (POSTECH)**, M.S. in Electrical Engineering (Mar. 2021 - Feb. 2023)
- **Soongsil University**, B.S. in Electronic Engineering, Summa Cum Laude (Mar. 2017 - Feb. 2021, GPA 4.3/4.5)

## Awards
- Mojgan Daneshmand Grant, IEEE AP-S/URSI 2024
- Student Travel Grant, IEEE AP-S/URSI 2024 (Declined)
- Best Paper Award (Student Paper Competition), KIEES Summer Symposium 2022

## Award Photo
<figure class="fig">
  <img src="{{ '/assets/img/award-photo.jpg' | relative_url }}" alt="Award photo at IEEE AP-S/URSI" loading="lazy">
  <figcaption>IEEE AP-S/URSI 2024 conference award moment.</figcaption>
</figure>

## Featured publications
{% assign featured_pubs = site.publications | where: "featured", true | sort: "year" | reverse %}
{% for p in featured_pubs %}
{% assign paper_href = p.pdf %}
{% if p.pdf and p.pdf contains '://' %}
  {% assign paper_href = p.pdf %}
{% elsif p.pdf %}
  {% assign paper_href = p.pdf | relative_url %}
{% endif %}
- **{{ p.title }}**  
  {{ p.authors }}  
  *{{ p.venue }}*, {{ p.year }}{% if p.month %} ({{ p.month }}){% endif %}.  
  {% if p.doi %}DOI: [{{ p.doi }}](https://doi.org/{{ p.doi }}){% endif %}{% if p.pdf %} · [paper]({{ paper_href }}){% endif %} · [details]({{ p.url | relative_url }})
{% endfor %}

## Featured projects
{% assign featured_projects = site.projects | where: "featured", true | sort: "year_end" | reverse %}
{% for pr in featured_projects %}
- **{{ pr.title }}** ({{ pr.period }})  
  {{ pr.summary }}  
  {% if pr.keywords %}Keywords: {{ pr.keywords | join: ", " }}{% endif %}  
  [details]({{ pr.url | relative_url }})
{% endfor %}

## Contact
If you’d like to discuss collaboration or opportunities, please reach out:
- Email: [myoungsunkim@postech.ac.kr](mailto:myoungsunkim@postech.ac.kr)
