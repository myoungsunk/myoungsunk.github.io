---
layout: default
title: "Myoungsun Kim"
permalink: /
---

{% assign featured_pubs = site.publications | where: "featured", true | sort: "year" | reverse %}
{% assign featured_projects = site.projects | where: "featured", true | sort: "year_end" | reverse %}

<div class="home-shell">
  <section class="hero-panel reveal">
    <p class="hero-kicker">RF Localization and Sensing</p>
    <h2>Reliable Indoor Positioning Under Real-World Constraints</h2>
    <p class="hero-lead">
      I am a Ph.D. student in Electrical Engineering at POSTECH (advisor: Prof. Wonbin Hong).
      My research focuses on RSS/RSSD-based DoA estimation, calibration, and RF system design for robust indoor localization.
    </p>
    <div class="hero-actions">
      <a class="action-btn" href="{{ '/publications/' | relative_url }}">View Publications</a>
      <a class="action-btn action-btn-light" href="{{ '/projects/' | relative_url }}">View Projects</a>
      <a class="action-btn action-btn-light" href="{{ '/assets/files/cv/CV_Myoungsunkim_25.05_ticra.html' | relative_url }}">Open CV</a>
    </div>
    <ul class="metric-chips">
      <li>POSTECH EE Ph.D.</li>
      <li>Indoor Localization</li>
      <li>DoA and Calibration</li>
      <li>RF Measurement Systems</li>
    </ul>
  </section>

  <section class="home-grid">
    <article class="focus-card reveal">
      <h3>Research Focus</h3>
      <p>Decentralized indoor localization using RSSD-based DoA and practical tag/system design.</p>
    </article>
    <article class="focus-card reveal">
      <h3>Methodology</h3>
      <p>Calibration and compensation pipelines for field-of-view constraints, bias, and multipath conditions.</p>
    </article>
    <article class="focus-card reveal">
      <h3>Engineering Scope</h3>
      <p>RF front-end and antenna measurement systems supporting robust communication and sensing.</p>
    </article>
  </section>

  <section class="timeline-panel reveal">
    <h3>Education</h3>
    <div class="timeline-item">
      <h4>POSTECH, Ph.D. in Electrical Engineering</h4>
      <p>Mar. 2023 - Present</p>
    </div>
    <div class="timeline-item">
      <h4>POSTECH, M.S. in Electrical Engineering</h4>
      <p>Mar. 2021 - Feb. 2023</p>
    </div>
    <div class="timeline-item">
      <h4>Soongsil University, B.S. in Electronic Engineering</h4>
      <p>Mar. 2017 - Feb. 2021, GPA 4.3/4.5 (Summa Cum Laude)</p>
    </div>
  </section>

  <section class="award-panel reveal">
    <div>
      <h3>Awards</h3>
      <ul class="clean-list">
        <li>Mojgan Daneshmand Grant, IEEE AP-S/URSI 2024</li>
        <li>Student Travel Grant, IEEE AP-S/URSI 2024 (Declined)</li>
        <li>Best Paper Award, KIEES Summer Symposium 2022</li>
      </ul>
    </div>
    <figure class="award-photo">
      <img src="{{ '/assets/img/award-photo.jpg' | relative_url }}" alt="Award photo at IEEE AP-S/URSI" loading="lazy">
      <figcaption>IEEE AP-S/URSI 2024 award moment.</figcaption>
    </figure>
  </section>

  <section class="list-panel reveal">
    <div class="section-head">
      <h3>Featured Publications</h3>
      <a href="{{ '/publications/' | relative_url }}">See all</a>
    </div>
    <div class="entry-list">
      {% for p in featured_pubs limit: 4 %}
      {% assign paper_href = p.pdf %}
      {% if p.pdf and p.pdf contains '://' %}
        {% assign paper_href = p.pdf %}
      {% elsif p.pdf %}
        {% assign paper_href = p.pdf | relative_url %}
      {% endif %}
      <article class="entry-card">
        <h4><a href="{{ p.url | relative_url }}">{{ p.title }}</a></h4>
        <p>{{ p.authors }}</p>
        <p><i>{{ p.venue }}</i>, {{ p.year }}{% if p.month %} ({{ p.month }}){% endif %}</p>
        <p>
          {% if p.doi %}<a href="https://doi.org/{{ p.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
          {% if p.pdf %} · <a href="{{ paper_href }}" target="_blank" rel="noopener">PDF</a>{% endif %}
        </p>
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="list-panel reveal">
    <div class="section-head">
      <h3>Featured Projects</h3>
      <a href="{{ '/projects/' | relative_url }}">See all</a>
    </div>
    <div class="entry-list">
      {% for pr in featured_projects limit: 4 %}
      <article class="entry-card">
        <h4><a href="{{ pr.url | relative_url }}">{{ pr.title }}</a></h4>
        <p>{{ pr.summary }}</p>
        <p>{{ pr.period }}</p>
        {% if pr.keywords %}<p class="keywords">{{ pr.keywords | join: " · " }}</p>{% endif %}
      </article>
      {% endfor %}
    </div>
  </section>

  <section class="contact-panel reveal">
    <h3>Contact</h3>
    <p>Email: <a href="mailto:myoungsunkim@postech.ac.kr">myoungsunkim@postech.ac.kr</a></p>
    <p>
      <a href="https://scholar.google.com/citations?user=fD7i2qgAAAAJ&hl=ko&oi=ao" target="_blank" rel="noopener">Google Scholar</a>
      ·
      <a href="https://github.com/myoungsunk" target="_blank" rel="noopener">GitHub</a>
      ·
      <a href="{{ '/assets/files/cv/CV_Myoungsunkim_25.05_ticra.docx' | relative_url }}">CV (DOCX)</a>
      ·
      <a href="{{ '/assets/files/curriculum_vitae.pdf' | relative_url }}">CV (PDF)</a>
    </p>
  </section>
</div>
