---
title: Projects
layout: default
permalink: /projects/
categories:
  - research
  - experience
  - projects
use_academicons: true
---

{%- for category in page.categories -%}
  <h1 class="section-title">{{ category | capitalize }}</h1>
  <ul class="post-list">
  {%- for project in site.projects -%}
    {%- if project.category != category -%}{% continue %}{%- endif -%}
    {%- if project.hidden -%}{%- continue -%}{%- endif -%}
    <li>

      <div class="row content-row">
        <div class="col-3">
          {%- if project.thumbnail -%}
            <img class="thumbnail rounded" src="{{ project.thumbnail }}">
          {%- endif -%}
          {%- if project.thumbnail_caption -%}
            <span class="caption">{{ project.thumbnail_caption }}</span>
          {%- endif -%}
        </div>

        <div class="col-9">
          <h2>
            {%- assign content = project.content | strip_newlines -%}
            {%- if content == "" -%}
              {{ project.title | escape | markdownify }}
            {%- else -%}
              <a class="post-link" href="{{ project.url | relative_url }}" title="{{ project.title }}">{{ project.title | escape | markdownify }}</a>
            {%- endif -%}
          </h2>

          {%- if project.setting -%}
            <p><i>{{ project.setting }}</i></p>
          {%- endif -%}

          {%- if project.team -%}
            <p><strong>Team:</strong> {{ project.team }}</p>
          {%- endif -%}

          {%- if project.mentors -%}
            <p><strong>Mentor(s):</strong> {{ project.mentors }}</p>
          {%- endif -%}

          {%- if project.collaborators -%}
            <p><strong>Collaborator(s):</strong> {{ project.collaborators }}</p>
          {%- endif -%}

          {%- if project.abstract -%}
            <p><strong>Abstract:</strong> {{ project.abstract }}</p>
          {%- endif -%}

          {%- if project.excerpt -%}
            <p>{{ project.excerpt }}</p>
          {%- endif -%}

          {%- if project.paper -%}
            <a href="{{ project.paper }}" class="btn btn-light">
              <i class="fas fa-file"></i> Paper
            </a>
          {%- endif -%}
          {%- if project.biorxiv -%}
            <a href="{{ project.biorxiv }}" class="btn btn-light">
              <i class="ai ai-biorxiv"></i> Preprint
            </a>
          {%- endif -%}
          {%- if project.demo -%}
            <a href="{{ project.demo }}" class="btn btn-light">
              <i class="fas fa-external-link-square-alt"></i> Demo
            </a>
          {%- endif -%}
          {%- if project.github -%}
            <a href="{{ project.github }}" class="btn btn-light">
              <i class="fab fa-github"></i> GitHub
            </a>
          {%- endif -%}
          {%- if project.video -%}
            <a href="{{ project.video }}" class="btn btn-light">
              <i class="fab fa-youtube"></i> Video
            </a>
          {%- endif -%}
        </div>
      </div>

    </li>
  {%- endfor -%}
  </ul>
{%- endfor -%}
