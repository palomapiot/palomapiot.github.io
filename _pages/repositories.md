---
layout: page
permalink: /repositories/
title: Repositories
description: 
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

## 🧠 Research Code & Open-Source Work

<div class="repo-section mb-5">

  <p class="lead">
    Reproducible research, datasets, benchmarks, and experimental tooling 
    for hate speech detection.
  </p>


  <div class="row">
    {% for user in site.data.repositories.github_users %}
      <div class="col-md-6 mb-3">
        <div class="card h-100 shadow-sm border-0 repo-card">
          <div class="card-body">
            <h5 class="card-title mb-2">
              <i class="fab fa-github me-2"></i>
              <a href="https://github.com/{{ user }}" class="stretched-link text-decoration-none">
                {{ user }}
              </a>
            </h5>
            <p class="card-text text-muted small mb-0">
              Open-source NLP research and experiments.
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

