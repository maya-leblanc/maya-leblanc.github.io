---
layout: page
title: projects
permalink: /projects/
nav: true
nav_order: 3
---

## robotics

{% assign robotics = site.projects | where: "category", "robotics" | sort: "importance" %}
{% for project in robotics %}
<div style="display:flex; gap:1.5rem; margin:2rem 0; align-items:flex-start; border-bottom: 1px solid #eee; padding-bottom:2rem;">
  {% if project.img %}
  <div style="min-width:150px; max-width:150px;">
    <img src="{{ project.img | relative_url }}" style="width:100%; border-radius:8px;" alt="{{ project.title }}">
  </div>
  {% endif %}
  <div>
    <strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
    <span style="color:gray; font-size:0.9rem;">{{ project.description }}</span>
  </div>
</div>
{% endfor %}

## engineering

{% assign engineering = site.projects | where: "category", "engineering" | sort: "importance" %}
{% for project in engineering %}
<div style="display:flex; gap:1.5rem; margin:2rem 0; align-items:flex-start; border-bottom: 1px solid #eee; padding-bottom:2rem;">
  {% if project.img %}
  <div style="min-width:150px; max-width:150px;">
    <img src="{{ project.img | relative_url }}" style="width:100%; border-radius:8px;" alt="{{ project.title }}">
  </div>
  {% endif %}
  <div>
    <strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
    <span style="color:gray; font-size:0.9rem;">{{ project.description }}</span>
  </div>
</div>
{% endfor %}

## research

{% assign research = site.projects | where: "category", "research" | sort: "importance" %}
{% for project in research %}
<div style="display:flex; gap:1.5rem; margin:2rem 0; align-items:flex-start; border-bottom: 1px solid #eee; padding-bottom:2rem;">
  {% if project.img %}
  <div style="min-width:150px; max-width:150px;">
    <img src="{{ project.img | relative_url }}" style="width:100%; border-radius:8px;" alt="{{ project.title }}">
  </div>
  {% endif %}
  <div>
    <strong><a href="{{ project.url | relative_url }}">{{ project.title }}</a></strong><br>
    <span style="color:gray; font-size:0.9rem;">{{ project.description }}</span>
  </div>
</div>
{% endfor %}
