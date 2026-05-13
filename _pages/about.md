---
permalink: /
title: ""
lang: en
alt_url: /zh/
author_profile: true
description: "English academic homepage of Zhenjian Wu with a full Chinese mirror page."
redirect_from:
  - /about/
  - /about.html
---

{% assign profile_text = site.data.profile.en %}
{% assign published = site.publications | where: "category", "published" | sort: "date" | reverse %}
{% assign working = site.publications | where: "category", "working" | sort: "date" | reverse %}
{% assign data_projects = site.projects | where: "group", "data" | sort: "date" | reverse %}
{% assign methods_projects = site.projects | where: "group", "methods" | sort: "date" | reverse %}

<span class="anchor" id="about-me"></span>
<section class="content-section content-section--intro">
  <p class="section-kicker">About Me</p>
  <p>{{ profile_text.bio }}</p>
  <p>{{ profile_text.credential_line }}</p>
  <p>{{ profile_text.bio_extra }}</p>
  <div class="overview-grid">
    {% for card in profile_text.overview_cards %}
    <article class="overview-card">
      <h3>{{ card.title }}</h3>
      <p>{{ card.body }}</p>
    </article>
    {% endfor %}
  </div>
</section>

<span class="anchor" id="research-interests"></span>
<section class="content-section">
  <h2>Research Interests</h2>
  <div class="interest-grid">
    {% for item in site.data.profile.research_interests %}
    <article class="interest-item">
      <h3>{{ item.en }}</h3>
      <p>{{ item.desc_en }}</p>
    </article>
    {% endfor %}
  </div>
</section>

<span class="anchor" id="publications"></span>
<section class="content-section">
  <h2>Publications</h2>
  {% for item in published %}
  <article class="paper-box">
    <div class="paper-box__year">
      <span class="paper-year-badge">{{ item.year }}</span>
    </div>
    <div class="paper-box__body">
      <h3>{{ item.title_en }}</h3>
      <p class="paper-meta">{{ item.authors_en }}</p>
      <p class="paper-venue"><em>{{ item.venue_en }}</em> · {{ item.status_en }}</p>
      <p>{{ item.summary_en }}</p>
      {% if item.doi %}
      <p class="paper-link"><a href="https://doi.org/{{ item.doi }}">DOI: {{ item.doi }}</a></p>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</section>

<span class="anchor" id="working-papers"></span>
<section class="content-section">
  <h2>Working Papers</h2>
  {% for item in working %}
  <article class="paper-box">
    <div class="paper-box__year">
      <span class="paper-year-badge paper-year-badge--muted">{{ item.year }}</span>
    </div>
    <div class="paper-box__body">
      <h3>{{ item.title_en }}</h3>
      <p class="paper-meta">{{ item.authors_en }}</p>
      <p class="paper-venue"><em>{{ item.venue_en }}</em> · {{ item.status_en }}</p>
      <p>{{ item.summary_en }}</p>
    </div>
  </article>
  {% endfor %}
</section>

<span class="anchor" id="research-resources"></span>
<section class="content-section">
  <h2>Research Resources</h2>
  <div class="resource-group">
    <h3>Data Resources</h3>
    {% for item in data_projects %}
    <article class="resource-entry">
      <h4>{{ item.title_en }}</h4>
      <p>{{ item.description_en }}</p>
      <p class="resource-note">{{ item.note_en }}</p>
    </article>
    {% endfor %}
  </div>
  <div class="resource-group">
    <h3>Methods</h3>
    {% for item in methods_projects %}
    <article class="resource-entry">
      <h4>{{ item.title_en }}</h4>
      <p>{{ item.description_en }}</p>
      <p class="resource-note">{{ item.note_en }}</p>
    </article>
    {% endfor %}
  </div>
</section>

<span class="anchor" id="educations"></span>
<section class="content-section">
  <h2>Educations</h2>
  <ul class="timeline-list">
    {% for item in site.data.profile.education %}
    <li>
      <span class="timeline-date">{{ item.date_en }}</span>
      <div>
        <strong>{{ item.institution_en }}</strong>
        <p>{{ item.degree_en }}</p>
      </div>
    </li>
    {% endfor %}
  </ul>
</section>
