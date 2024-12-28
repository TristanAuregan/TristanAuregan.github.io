---
layout: default
title: Publications
permalink: /publications/
order: 1
refactor: true
icon: fa-solid fa-newspaper
---

# Publications
<style>
    .card-text {
        line-height: 1.2;
        font-size: 16px;
        color: var(--text-color);
    }
    .card-title {
        font-weight: bold;
        color: var(--text-color);
    }
    .card-text .fas {
        display: inline;
        margin-right: 5px;
        color: var(--text-color);
    }
    .card-text p {
        display: inline;
        margin: 0;
        color: var(--text-color);
    }
    
    /* Add styles for clickable card */
    .card-wrapper {
        transition: transform 0.2s;
        cursor: pointer;
    }
    .card-wrapper:hover {
        transform: scale(1.01);
    }
</style>

<div class="row">
  <div class="col-12 col-lg-11">
    <div id="post-list" class="flex-grow-1 px-xl-1">
      {% for item in site.data.publications %}
        <article class="card-wrapper card" onclick="window.open('{{ item.url }}', '_blank')" style="cursor: pointer;">
          <div class="post-preview row g-0 flex-md-row-reverse">
            {% if item.image %}
              <div class="col-md-5">
                <div class="preview-img">
                  <img src="{{ item.image | relative_url }}" alt="{{ item.title | xml_escape }}" loading="lazy">
                </div>
              </div>
              {% assign content_col = '7' %}
            {% else %}
              {% assign content_col = '12' %}
            {% endif %}

            <div class="col-md-{{ content_col }}">
              <div class="card-body d-flex flex-column">
                <h2 class="card-title my-2 mt-md-0">{{ item.title }}</h2>

                <div class="card-text content mt-0 mb-3">
                  {{ item.description }}
                </div>

                <div class="card-text content mt-0 mb-3">
                  <i class="fas fa-link"></i>
                  {{ item.reference | markdownify }}
                </div>
              </div>
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
  </div>
</div>