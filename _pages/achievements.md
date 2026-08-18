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
    gap: 1.15rem;
    padding-top: 0.8rem;
  }

  .wk-achievement-card h2 {
    margin: 0 0 1.2rem;
    color: var(--global-text-color);
    font-family: "Newsreader", Georgia, serif !important;
    font-size: 1.42rem;
    font-weight: 500;
    letter-spacing: -0.04em;
  }

  .wk-achievement-item {
    display: grid;
    grid-template-columns: 92px minmax(0, 1fr);
    gap: 1.35rem;
    padding: 1rem 0;
  }

  .wk-achievement-item + .wk-achievement-item {
    border-top: 1px solid var(--global-divider-color);
  }

  .wk-achievement-year {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.83rem;
    font-weight: 500;
  }

  .wk-achievement-title {
    margin-bottom: 0.16rem;
    color: var(--global-text-color);
    font-size: 0.98rem;
    font-weight: 600;
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
    font-size: 0.86rem;
    font-weight: 400;
    line-height: 1.6;
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
