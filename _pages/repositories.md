---
layout: page
permalink: /repositories/
title: Repositories
description: 
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

## GitHub

<ul class="list-unstyled">
  {% for user in site.data.repositories.github_users %}
    <li class="mb-2">
      <a href="https://github.com/{{ user }}">
        <strong>{{ user }}</strong>
      </a>
    </li>
  {% endfor %}
</ul>

{% endif %}


{% if site.data.repositories.github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
