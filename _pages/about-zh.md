---
permalink: /zh/
title: ""
lang: zh
alt_url: /
author_profile: true
description: "武振建中文学术主页，英文版为默认入口。"
---

{% assign profile_text = site.data.profile.zh %}
{% assign published = site.publications | where: "category", "published" | sort: "date" | reverse %}
{% assign working = site.publications | where: "category", "working" | sort: "date" | reverse %}
{% assign research_projects = site.projects | where: "group", "research" | sort: "date" | reverse %}
{% assign data_projects = site.projects | where: "group", "data" | sort: "date" | reverse %}
{% assign methods_projects = site.projects | where: "group", "methods" | sort: "date" | reverse %}
{% assign collaboration_projects = site.projects | where: "group", "collaboration" | sort: "date" | reverse %}

<span class="anchor" id="about-me"></span>
<section class="content-section content-section--intro">
  <p class="section-kicker">关于我</p>
  <p>{{ profile_text.bio }}</p>
  <p>{{ profile_text.credential_line }}</p>
  <p>{{ profile_text.bio_extra }}</p>
  <p class="signature-line">{{ profile_text.signature_line }}</p>
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
  <h2>研究方向</h2>
  <div class="interest-grid">
    {% for item in site.data.profile.research_interests %}
    <article class="interest-item">
      <h3>{{ item.zh }}</h3>
      <p>{{ item.desc_zh }}</p>
    </article>
    {% endfor %}
  </div>
</section>

<span class="anchor" id="publications"></span>
<section class="content-section">
  <h2>已发表论文</h2>
  {% for item in published %}
  <article class="paper-box">
    <div class="paper-box__year">
      <span class="paper-year-badge">{{ item.year }}</span>
    </div>
    <div class="paper-box__body">
      <h3>{{ item.title_zh }}</h3>
      <p class="paper-meta">{{ item.authors_zh }}</p>
      <p class="paper-venue"><em>{{ item.venue_zh }}</em> · {{ item.status_zh }}</p>
      <p>{{ item.summary_zh }}</p>
      {% if item.doi %}
      <p class="paper-link"><a href="https://doi.org/{{ item.doi }}">DOI: {{ item.doi }}</a></p>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</section>

<span class="anchor" id="working-papers"></span>
<section class="content-section">
  <h2>工作论文</h2>
  {% for item in working %}
  <article class="paper-box">
    <div class="paper-box__year">
      <span class="paper-year-badge paper-year-badge--muted">{{ item.year }}</span>
    </div>
    <div class="paper-box__body">
      <h3>{{ item.title_zh }}</h3>
      <p class="paper-meta">{{ item.authors_zh }}</p>
      <p class="paper-venue"><em>{{ item.venue_zh }}</em> · {{ item.status_zh }}</p>
      <p>{{ item.summary_zh }}</p>
    </div>
  </article>
  {% endfor %}
</section>

<span class="anchor" id="research-resources"></span>
<section class="content-section">
  <h2>研究资源</h2>
  <div class="resource-group">
    <h3>科研项目</h3>
    {% for item in research_projects %}
    <article class="resource-entry">
      <h4>{{ item.title_zh }}</h4>
      <p>{{ item.description_zh }}</p>
      <p class="resource-note">{{ item.note_zh }}</p>
    </article>
    {% endfor %}
  </div>
  <div class="resource-group">
    <h3>数据资源</h3>
    {% for item in data_projects %}
    <article class="resource-entry">
      <h4>{{ item.title_zh }}</h4>
      <p>{{ item.description_zh }}</p>
      <p class="resource-note">{{ item.note_zh }}</p>
    </article>
    {% endfor %}
  </div>
  <div class="resource-group">
    <h3>方法能力</h3>
    {% for item in methods_projects %}
    <article class="resource-entry">
      <h4>{{ item.title_zh }}</h4>
      <p>{{ item.description_zh }}</p>
      <p class="resource-note">{{ item.note_zh }}</p>
    </article>
    {% endfor %}
  </div>
</section>

<span class="anchor" id="educations"></span>
<section class="content-section">
  <h2>教育背景</h2>
  <ul class="timeline-list">
    {% for item in site.data.profile.education %}
    <li>
      <span class="timeline-date">{{ item.date }}</span>
      <div>
        <strong>{{ item.institution_zh }}</strong>
        <p>{{ item.degree_zh }}</p>
      </div>
    </li>
    {% endfor %}
  </ul>
</section>

<span class="anchor" id="collaboration"></span>
<section class="content-section">
  <h2>合作</h2>
  <p>{{ profile_text.collaboration }}</p>
  {% for item in collaboration_projects %}
  <article class="resource-entry">
    <h4>{{ item.title_zh }}</h4>
    <p>{{ item.description_zh }}</p>
    <p class="resource-note">{{ item.note_zh }}</p>
  </article>
  {% endfor %}
</section>

<span class="anchor" id="contact"></span>
<section class="content-section">
  <h2>联系</h2>
  <p>当前站点仅公开邮箱，不提供私人资料下载。</p>
  <p><a href="mailto:{{ profile_text.email }}">{{ profile_text.email }}</a></p>
  <p>{{ profile_text.affiliation }} · {{ profile_text.location }}</p>
</section>
