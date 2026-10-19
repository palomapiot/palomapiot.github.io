---
layout: page
title: Other Activities
permalink: /activities/
description: Other activities I take part in.
nav: true
nav_order: 3
display_categories: [work]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
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

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

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

<!-- Activity lists, from _data/activities.yml -->
<div class="activities">
{% for group in site.data.activities %}
  <section class="activity-section">
    <h2 class="category">{{ group.section }}</h2>
    <ul class="activity-list{% if group.compact %} compact{% endif %}">
    {% for item in group.items %}
      <li class="activity-item">
        {% if item.date %}<span class="activity-date">{{ item.date }}</span>{% endif %}
        <div class="activity-body">
          <span class="activity-title">{{ item.title }}</span>
          {% if item.event %}<span class="activity-event">{{ item.event }}</span>{% endif %}
          {% if item.note %}<span class="activity-note">{{ item.note }}</span>{% endif %}
          {% if item.links %}
          <span class="activity-links">
            {% for link in item.links %}<a href="{{ link.url }}" target="_blank" rel="noopener">{{ link.label }}</a>{% endfor %}
          </span>
          {% endif %}
        </div>
      </li>
    {% endfor %}
    </ul>
  </section>
{% endfor %}
</div>
