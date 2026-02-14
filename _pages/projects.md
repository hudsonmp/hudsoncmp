---
layout: page
title: projects
permalink: /projects/
description: A growing collection of projects and hackathons.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<!-- Hackathons -->
<div class="projects">
{% assign sorted_hackathons = site.hackathons | sort: "importance" %}

  <div class="row row-cols-1 row-cols-md-3">
    {% for hackathon in sorted_hackathons %}
      {% include hackathons.liquid %}
    {% endfor %}
  </div>
</div>

<!-- Projects (hidden for now)
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}
{% else %}
{% assign sorted_projects = site.projects | sort: "importance" %}
{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
-->
