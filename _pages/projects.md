---
layout: default
title: projects
permalink: /projects/
nav: true
nav_order: 3
---

<div class="post">
  <header class="post-header">
    <h1 class="post-title">projects</h1>
  </header>

  <article>

<h2>robotics</h2>
{% assign robotics = site.projects | where: "category", "robotics" | sort: "importance" %}
{% for project in robotics %}
<div style="display:flex;gap:1.5rem;margin:2rem 0;align-items:flex-start;border-bottom:1px solid #eee;padding-bottom:2rem;">
{% if project.img %}
<div style="min-width:150px;max-width:150px;flex-shrink:0;">
<img src="{{ project.img | relative_url }}" style="width:100%;border-radius:8px;object-fit:cover;" alt="{{ project.title }}">
</div>
{% endif %}
<div>
<strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
<span style="color:gray;font-size:0.9rem;">{{ project.description }}</span>
</div>
</div>
{% endfor %}

<h2>research</h2>
{% assign research = site.projects | where: "category", "research" | sort: "importance" %}
{% for project in research %}
<div style="display:flex;gap:1.5rem;margin:2rem 0;align-items:flex-start;border-bottom:1px solid #eee;padding-bottom:2rem;">
{% if project.img %}
<div style="min-width:150px;max-width:150px;flex-shrink:0;">
<img src="{{ project.img | relative_url }}" style="width:100%;border-radius:8px;object-fit:cover;" alt="{{ project.title }}">
</div>
{% endif %}
<div>
<strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
<span style="color:gray;font-size:0.9rem;">{{ project.description }}</span>
</div>
</div>
{% endfor %}

<h2>engineering</h2>
{% assign engineering = site.projects | where: "category", "engineering" | sort: "importance" %}
{% for project in engineering %}
<div style="display:flex;gap:1.5rem;margin:2rem 0;align-items:flex-start;border-bottom:1px solid #eee;padding-bottom:2rem;">
{% if project.img %}
<div style="min-width:150px;max-width:150px;flex-shrink:0;">
<img src="{{ project.img | relative_url }}" style="width:100%;border-radius:8px;object-fit:cover;" alt="{{ project.title }}">
</div>
{% endif %}
<div>
<strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
<span style="color:gray;font-size:0.9rem;">{{ project.description }}</span>
</div>
</div>
{% endfor %}

  </article>
</div>
