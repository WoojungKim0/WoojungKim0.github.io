---
layout: page
title: Achievements
permalink: /achievements/
nav: true
nav_order: 4
---

<style>
  .wk-achievements {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    padding-top: 0.35rem;
  }

  .wk-achievement-card h2 {
    margin: 0 0 0.9rem;
    color: var(--global-text-color);
    font-size: 1.05rem;
    font-weight: 400;
    letter-spacing: -0.025em;
  }

  .wk-achievement-item {
    display: grid;
    grid-template-columns: 88px minmax(0, 1fr);
    gap: 1.2rem;
    padding: 0.85rem 0;
  }

  .wk-achievement-item + .wk-achievement-item {
    border-top: 1px solid var(--global-divider-color);
  }

  .wk-achievement-year {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.78rem;
    font-weight: 300;
  }

  .wk-achievement-title {
    margin-bottom: 0.12rem;
    color: var(--global-text-color);
    font-size: 0.9rem;
    font-weight: 500;
    letter-spacing: -0.015em;
    line-height: 1.45;
  }

  .wk-achievement-title a {
    color: inherit;
    text-decoration: none;
  }

  .wk-achievement-title a:hover {
    color: var(--global-theme-color);
  }

  .wk-achievement-meta {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.8rem;
    font-weight: 300;
    line-height: 1.55;
  }

  @media (max-width: 620px) {
    .wk-achievement-item {
      grid-template-columns: 1fr;
      gap: 0.2rem;
    }
  }
</style>

<div class="wk-achievements">
  {% for section in site.data.achievements.sections %}
    {% if section.items.size > 0 %}
      <section class="wk-section-card wk-achievement-card">
        <h2>{{ section.title }}</h2>
        <div>
          {% for item in section.items %}
            <article class="wk-achievement-item">
              <div class="wk-achievement-year">{{ item.year }}</div>
              <div>
                <div class="wk-achievement-title">
                  {% if item.url and item.url != "" %}
                    <a href="{{ item.url }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>
                  {% else %}
                    {{ item.title }}
                  {% endif %}
                </div>
                {% if item.organization and item.organization != "" %}
                  <div class="wk-achievement-meta">{{ item.organization }}</div>
                {% endif %}
                {% if item.detail and item.detail != "" %}<div class="wk-achievement-meta">{{ item.detail }}</div>{% endif %}
              </div>
            </article>
          {% endfor %}
        </div>
      </section>
    {% endif %}
  {% endfor %}
</div>
