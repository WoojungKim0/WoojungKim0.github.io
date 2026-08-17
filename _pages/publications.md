---
layout: page
title: Research
permalink: /research/
description: Research in empirical asset pricing and AI in finance.
nav: true
nav_order: 2
---

<style>
  .wk-research {
    padding-top: 0.5rem;
  }

  .wk-research-intro {
    max-width: 720px;
    margin: 0 0 1.35rem;
    color: var(--global-text-color-light);
    font-size: 0.86rem;
    font-weight: 300;
    line-height: 1.7;
  }

  .wk-research-filter {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 3rem;
  }

  .wk-filter-button {
    padding: 0.38rem 0.82rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    background: transparent;
    color: var(--global-text-color);
    font: inherit;
    font-size: 0.78rem;
    font-weight: 300;
    line-height: 1.25;
    cursor: pointer;
    transition:
      border-color 0.16s ease,
      background-color 0.16s ease,
      color 0.16s ease;
  }

  .wk-filter-button:hover {
    border-color: var(--global-theme-color);
    color: var(--global-theme-color);
  }

  .wk-filter-button.is-active {
    border-color: var(--global-theme-color);
    background: var(--global-theme-color);
    color: #fff;
  }

  .wk-research-section {
    margin-bottom: 3.75rem;
  }

  .wk-research-section h2 {
    margin: 0 0 1.25rem;
    color: var(--global-text-color);
    font-size: 1.16rem;
    font-weight: 300;
    letter-spacing: -0.03em;
  }

  .wk-paper-list {
    counter-reset: paper;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .wk-paper {
    counter-increment: paper;
    display: grid;
    grid-template-columns: 46px minmax(0, 1fr);
    gap: 0.65rem;
    padding: 1rem 1.1rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 9px;
    background: var(--wk-panel-bg-color);
    box-shadow: var(--wk-panel-shadow);
    transition:
      border-color 0.16s ease,
      background-color 0.16s ease,
      box-shadow 0.16s ease;
  }

  .wk-paper:hover {
    border-color: var(--global-theme-color);
    background: var(--global-card-bg-color);
    box-shadow: 0 3px 10px rgba(11, 18, 21, 0.04);
  }

  .wk-paper::before {
    content: counter(paper, decimal-leading-zero);
    padding-top: 0.18rem;
    color: rgba(11, 18, 21, 0.43);
    font-size: 0.82rem;
    font-weight: 300;
    letter-spacing: 0.06em;
  }

  .wk-paper-title {
    margin: 0 0 0.2rem;
    color: var(--global-text-color);
    font-size: clamp(0.98rem, 2vw, 1.08rem);
    font-weight: 600;
    letter-spacing: -0.02em;
    line-height: 1.4;
  }

  .wk-paper-authors,
  .wk-paper-venue {
    margin: 0;
    color: rgba(11, 18, 21, 0.66);
    font-size: 0.8rem;
    font-weight: 300;
    line-height: 1.5;
  }

  .wk-paper-venue {
    color: var(--global-text-color);
  }

  .wk-paper-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 0.28rem;
    font-size: 0.76rem;
    font-weight: 300;
  }

  .wk-paper-links a,
  .wk-abstract-toggle {
    border: 0;
    background: transparent;
    color: var(--global-theme-color);
    font: inherit;
    text-decoration: none;
    cursor: pointer;
    transition: color 0.16s ease;
  }

  .wk-abstract-toggle {
    padding: 0;
  }

  .wk-paper-links a:hover,
  .wk-abstract-toggle:hover {
    color: var(--global-hover-color);
  }

  .wk-paper-links > * + *::before {
    content: "·";
    padding: 0 0.55rem;
    color: var(--global-text-color-light);
  }

  .wk-abstract-chevron {
    display: inline-block;
    margin-left: 0.15rem;
    transition: transform 0.16s ease;
  }

  .wk-abstract-toggle[aria-expanded="true"] .wk-abstract-chevron {
    transform: rotate(180deg);
  }

  .wk-paper-abstract {
    max-width: 760px;
    margin-top: 0.55rem;
    padding-left: 0.8rem;
    border-left: 1px solid var(--global-divider-color);
    color: var(--global-text-color-light);
    font-size: 0.76rem;
    font-weight: 300;
    line-height: 1.65;
  }

  .wk-paper-abstract p {
    margin: 0;
  }

  .wk-empty {
    margin: 0;
    padding: 1rem 1.1rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 9px;
    background: var(--wk-panel-bg-color);
    box-shadow: var(--wk-panel-shadow);
    color: var(--global-text-color-light);
    font-size: 0.8rem;
    font-weight: 300;
  }

  @media (max-width: 560px) {
    .wk-research-filter {
      margin-bottom: 2.4rem;
    }

    .wk-paper {
      grid-template-columns: 34px minmax(0, 1fr);
      padding: 0.9rem 0.85rem;
    }

    .wk-empty {
      padding: 0.9rem 0.85rem;
    }
  }
</style>

<div class="wk-research">
  <p class="wk-research-intro">
    My research centers on empirical asset pricing, factor investing, cross-asset predictability, and machine learning applications in financial
    markets.
  </p>

  <div class="wk-research-filter" role="group" aria-label="Filter research by field">
    <button class="wk-filter-button is-active" type="button" data-filter="all" aria-pressed="true">All</button>
    <button class="wk-filter-button" type="button" data-filter="finance" aria-pressed="false">Finance</button>
    <button class="wk-filter-button" type="button" data-filter="engineering" aria-pressed="false">Engineering</button>
  </div>

  <section class="wk-research-section" data-paper-section="published">
    <h2>Published Papers</h2>
    <div class="wk-paper-list">
      {% for paper in site.data.research.published %}
        <article class="wk-paper" data-area="{{ paper.area | default: 'finance' }}">
          <div>
            <h3 class="wk-paper-title">{{ paper.title }}</h3>
            <p class="wk-paper-authors">{{ paper.authors }}</p>
            <p class="wk-paper-venue">
              {{ paper.journal }}{% if paper.volume %}, {{ paper.volume }}{% endif %}{% if paper.article %}, {{ paper.article }}{% endif %} · {{ paper.year }}
            </p>
            <div class="wk-paper-links">
              {% if paper.publisher_url %}<a href="{{ paper.publisher_url }}" target="_blank" rel="noopener noreferrer">Publisher</a>{% endif %}
              {% if paper.ssrn_url %}<a href="{{ paper.ssrn_url }}" target="_blank" rel="noopener noreferrer">SSRN</a>{% endif %}
              {% if paper.abstract %}
                <button class="wk-abstract-toggle" type="button" aria-expanded="false" aria-controls="published-abstract-{{ forloop.index }}">
                  Abstract <span class="wk-abstract-chevron" aria-hidden="true">&#9662;</span>
                </button>
              {% endif %}
            </div>
            {% if paper.abstract %}
              <div class="wk-paper-abstract" id="published-abstract-{{ forloop.index }}" hidden><p>{{ paper.abstract }}</p></div>
            {% endif %}
          </div>
        </article>
      {% endfor %}
    </div>
    <p class="wk-empty" hidden>No published papers are listed for this field.</p>
  </section>

  <section class="wk-research-section" data-paper-section="working">
    <h2>Working Papers</h2>
    <div class="wk-paper-list">
      {% for paper in site.data.research.working %}
        <article class="wk-paper" data-area="{{ paper.area | default: 'finance' }}">
          <div>
            <h3 class="wk-paper-title">{{ paper.title }}</h3>
            <p class="wk-paper-authors">{{ paper.authors }}</p>
            {% if paper.status %}<p class="wk-paper-venue">{{ paper.status }}</p>{% endif %}
            <div class="wk-paper-links">
              {% if paper.publisher_url %}<a href="{{ paper.publisher_url }}" target="_blank" rel="noopener noreferrer">Publisher</a>{% endif %}
              {% if paper.ssrn_url %}<a href="{{ paper.ssrn_url }}" target="_blank" rel="noopener noreferrer">SSRN</a>{% endif %}
              {% if paper.abstract %}
                <button class="wk-abstract-toggle" type="button" aria-expanded="false" aria-controls="working-abstract-{{ forloop.index }}">
                  Abstract <span class="wk-abstract-chevron" aria-hidden="true">&#9662;</span>
                </button>
              {% endif %}
            </div>
            {% if paper.abstract %}
              <div class="wk-paper-abstract" id="working-abstract-{{ forloop.index }}" hidden><p>{{ paper.abstract }}</p></div>
            {% endif %}
          </div>
        </article>
      {% endfor %}
    </div>
    <p class="wk-empty" hidden>No working papers are listed for this field.</p>
  </section>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const filterButtons = document.querySelectorAll(".wk-filter-button");
    const sections = document.querySelectorAll("[data-paper-section]");

    function applyFilter(filter) {
      filterButtons.forEach(function (button) {
        const isActive = button.dataset.filter === filter;
        button.classList.toggle("is-active", isActive);
        button.setAttribute("aria-pressed", String(isActive));
      });

      sections.forEach(function (section) {
        const papers = section.querySelectorAll(".wk-paper");
        let visibleCount = 0;
        papers.forEach(function (paper) {
          const isVisible = filter === "all" || paper.dataset.area === filter;
          paper.hidden = !isVisible;
          if (isVisible) visibleCount += 1;
        });
        section.querySelector(".wk-empty").hidden = visibleCount > 0;
      });
    }

    filterButtons.forEach(function (button) {
      button.addEventListener("click", function () {
        applyFilter(button.dataset.filter);
      });
    });

    document.querySelectorAll(".wk-abstract-toggle").forEach(function (button) {
      button.addEventListener("click", function () {
        const abstract = document.getElementById(button.getAttribute("aria-controls"));
        const willOpen = button.getAttribute("aria-expanded") !== "true";
        button.setAttribute("aria-expanded", String(willOpen));
        abstract.hidden = !willOpen;
      });
    });

    applyFilter("all");
  });
</script>
