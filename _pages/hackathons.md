---
layout: page
title: hackathons
permalink: /hackathons/
description: a collection of hackathon projects.
nav: false
nav_order: 4
horizontal: false
---

<!-- pages/hackathons.md -->
<div class="projects">
{% assign sorted_hackathons = site.hackathons | sort: "importance" %}

  <div class="row row-cols-1 row-cols-md-3">
    {% for hackathon in sorted_hackathons %}
      {% include hackathons.liquid %}
    {% endfor %}
  </div>
</div>
