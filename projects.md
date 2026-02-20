---
layout: single
title: "Projects"
permalink: /projects/
---

This page is generated from `_data/projects.yml`.

{% assign ps = site.data.projects | sort: "year_end" | reverse %}
{% for pr in ps %}
## {{ pr.title }}
**Period:** {{ pr.period }}  
**Summary:** {{ pr.summary }}  
**Keywords:** {{ pr.keywords | join: ", " }}  
{% if pr.links.paper %}**Related paper:** [link]({{ pr.links.paper }}){% endif %}

**My contribution (fill in):**
{% for t in pr.my_contribution_todo %}
- {{ t }}
{% endfor %}

**Optional demo ideas (Codex-friendly):**
{% for d in pr.demo_idea %}
- {{ d }}
{% endfor %}

---
{% endfor %}
