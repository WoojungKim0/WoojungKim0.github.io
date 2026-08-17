---
layout: page
title: Achievements
permalink: /achievements/
nav: true
nav_order: 4
---

<style>
  .wk-achievement-section {
    margin-bottom: 3rem;
  }

  .wk-achievement-section h2 {
    font-size: 1.35rem;
    font-weight: 650;
    margin-bottom: 1.15rem;
    padding-bottom: 0.55rem;
    border-bottom: 1px solid var(--global-divider-color, #e5e7eb);
  }

  .wk-achievement-item {
    display: grid;
    grid-template-columns: 90px minmax(0, 1fr);
    gap: 1.2rem;
    padding: 1rem 0;
    border-bottom: 1px solid var(--global-divider-color, #e5e7eb);
  }

  .wk-achievement-year {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.93rem;
  }

  .wk-achievement-title {
    font-weight: 600;
    margin-bottom: 0.15rem;
  }

  .wk-achievement-meta {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.93rem;
  }

  @media (max-width: 620px) {
    .wk-achievement-item {
      grid-template-columns: 1fr;
      gap: 0.25rem;
    }
  }
</style>


<section class="wk-achievement-section">

  <h2>Awards & Honors</h2>

  {% for item in site.data.achievements.awards %}

  <div class="wk-achievement-item">

    <div class="wk-achievement-year">
      {{ item.year }}
    </div>

    <div>

      <div class="wk-achievement-title">
        {{ item.title }}
      </div>

      <div class="wk-achievement-meta">
        {{ item.organization }}
      </div>

      {% if item.detail and item.detail != "" %}
      <div class="wk-achievement-meta">
        {{ item.detail }}
      </div>
      {% endif %}

    </div>

  </div>

  {% endfor %}

</section>


<section class="wk-achievement-section">

  <h2>Patents</h2>

  {% for item in site.data.achievements.patents %}

  <div class="wk-achievement-item">

    <div class="wk-achievement-year">
      {{ item.year }}
    </div>

    <div>

      <div class="wk-achievement-title">
        {{ item.title }}
      </div>

      {% if item.number and item.number != "" %}
      <div class="wk-achievement-meta">
        {{ item.number }}
      </div>
      {% endif %}

      {% if item.inventors and item.inventors != "" %}
      <div class="wk-achievement-meta">
        {{ item.inventors }}
      </div>
      {% endif %}

      {% if item.detail and item.detail != "" %}
      <div class="wk-achievement-meta">
        {{ item.detail }}
      </div>
      {% endif %}

    </div>

  </div>

  {% endfor %}

</section>
