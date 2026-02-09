---
layout: page
permalink: /repositories/
title: Repositories
description: 
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

## Code & Repositories

<div class="repo-section mb-5">

  <p class="text-muted">
    Open-source implementations and experimental code accompanying my research.
  </p>

  <div class="row">
    {% for user in site.data.repositories.github_users %}
      <div class="col-md-6 mb-3">
        <div class="card h-100 shadow-sm">
          <div class="card-body">
            <h5 class="card-title mb-1">
              <a href="https://github.com/{{ user }}">{{ user }}</a>
            </h5>
            <p class="card-text text-muted small mb-0">
              GitHub profile
            </p>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>

</div>

{% endif %}

{% if site.data.repositories.github_repos %}

### Selected repositories

<div class="row">
  {% for repo in site.data.repositories.github_repos %}
    <div class="col-md-6 mb-4">
      {% include repository/repo.liquid repository=repo %}
    </div>
  {% endfor %}
</div>

{% endif %}

