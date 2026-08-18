---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 2
---

<style>
  .wk-research {
    padding-top: 0.8rem;
  }

  .wk-research-filter {
    display: flex;
    flex-wrap: wrap;
    gap: 0.62rem;
    margin: 0 0 3.5rem;
  }

  .wk-filter-button {
    padding: 0.5rem 1rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 999px;
    background: var(--wk-panel-bg-color);
    box-shadow: 0 7px 20px rgba(32, 67, 94, 0.035);
    color: var(--global-text-color);
    font: inherit;
    font-size: 0.83rem;
    font-weight: 500;
    line-height: 1.25;
    cursor: pointer;
    transition:
      border-color 0.16s ease,
      background-color 0.16s ease,
      color 0.16s ease,
      transform 0.16s ease;
  }

  .wk-filter-button:hover {
    border-color: var(--global-theme-color, #1768ac);
    color: var(--global-theme-color, #1768ac);
    transform: translateY(-1px);
  }

  .wk-filter-button.is-active,
  .wk-filter-button[aria-pressed="true"] {
    border-color: var(--global-theme-color, #1768ac);
    background-color: var(--global-theme-color, #1768ac);
    color: #fff;
    box-shadow: 0 8px 20px color-mix(in srgb, var(--global-theme-color) 24%, transparent);
  }

  .wk-paper[hidden],
  .wk-empty[hidden],
  .wk-paper-abstract[hidden] {
    display: none !important;
  }

  .wk-research-section {
    margin-bottom: 4rem;
  }

  .wk-research-section h2 {
    margin: 0 0 1.25rem;
    color: var(--global-text-color);
    font-family: "Newsreader", Georgia, serif !important;
    font-size: 1.62rem;
    font-weight: 500;
    letter-spacing: -0.04em;
  }

  .wk-paper-list {
    counter-reset: paper;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .wk-paper {
    counter-increment: paper;
    display: grid;
    grid-template-columns: 44px minmax(0, 1fr);
    gap: 0.9rem;
    padding: 1.4rem 1.5rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 16px;
    background: var(--wk-panel-bg-color);
    box-shadow: var(--wk-panel-shadow);
    backdrop-filter: blur(14px) saturate(115%);
    transition:
      border-color 0.16s ease,
      background-color 0.16s ease,
      box-shadow 0.16s ease,
      transform 0.16s ease;
  }

  .wk-paper:hover {
    border-color: color-mix(in srgb, var(--global-theme-color) 34%, transparent);
    background: var(--global-card-bg-color);
    box-shadow: 0 20px 54px rgba(32, 67, 94, 0.085);
    transform: translateY(-2px);
  }

  .wk-paper::before {
    content: counter(paper, decimal-leading-zero);
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 2rem;
    height: 2rem;
    border: 1px solid color-mix(in srgb, var(--global-theme-color) 16%, transparent);
    border-radius: 50%;
    background: var(--wk-chip-bg-color);
    color: var(--global-theme-color);
    font-size: 0.76rem;
    font-weight: 500;
    letter-spacing: 0.06em;
  }

  .wk-paper-title {
    margin: 0 0 0.3rem;
    color: var(--global-text-color);
    font-size: clamp(1.06rem, 2vw, 1.16rem);
    font-weight: 600;
    letter-spacing: -0.025em;
    line-height: 1.42;
  }

  .wk-paper-authors,
  .wk-paper-venue,
  .wk-paper-note {
    margin: 0;
    color: var(--global-text-color-light);
    font-size: 0.86rem;
    font-weight: 400;
    line-height: 1.58;
  }

  .wk-paper-venue {
    color: var(--global-text-color);
  }

  .wk-paper-note {
    margin-top: 0.45rem;
  }

  .wk-paper-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 0.48rem;
    font-size: 0.82rem;
    font-weight: 500;
  }

  .wk-paper-links a,
  .wk-abstract-toggle {
    padding: 0;
    border: 0;
    background: transparent;
    color: var(--global-theme-color);
    font: inherit;
    text-decoration: none;
    cursor: pointer;
    transition: color 0.16s ease;
  }

  .wk-paper-links a:hover,
  .wk-abstract-toggle:hover {
    color: var(--global-hover-color);
  }

  .wk-paper-links > * + *::before {
    padding: 0 0.55rem;
    color: var(--global-text-color-light);
    content: "·";
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
    max-width: 800px;
    margin-top: 0.9rem;
    padding: 1rem 1.1rem;
    border: 1px solid color-mix(in srgb, var(--global-theme-color) 15%, transparent);
    border-left: 3px solid var(--global-theme-color);
    border-radius: 0 10px 10px 0;
    background: var(--wk-abstract-bg-color);
    color: var(--global-text-color-light);
    font-size: 0.84rem;
    font-weight: 400;
    line-height: 1.75;
  }

  .wk-paper-abstract p {
    margin: 0;
  }

  .wk-empty {
    margin: 0;
    padding: 1.2rem 1.35rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 14px;
    background: var(--wk-panel-bg-color);
    box-shadow: var(--wk-panel-shadow);
    color: var(--global-text-color-light);
    font-size: 0.84rem;
    font-weight: 300;
  }

  @media (max-width: 560px) {
    .wk-research-filter {
      margin-bottom: 2.5rem;
    }

    .wk-paper {
      grid-template-columns: 1fr;
      padding: 1.15rem 1rem;
    }

    .wk-paper::before {
      width: 1.75rem;
      height: 1.75rem;
    }

    .wk-empty {
      padding: 1rem 0.9rem;
    }
  }
</style>

<div class="wk-research">
  <div class="wk-research-filter" role="group" aria-label="Filter research by field">
    {% for filter in site.data.research.filters %}
      <button
        class="wk-filter-button{% if filter.id == 'all' %} is-active{% endif %}"
        type="button"
        data-filter="{{ filter.id }}"
        aria-pressed="{% if filter.id == 'all' %}true{% else %}false{% endif %}"
      >
        {{ filter.label }}
      </button>
    {% endfor %}
  </div>

{% for section in site.data.research.sections %}

<section class="wk-research-section" data-paper-section="{{ section.id }}">
<h2>{{ section.title }}</h2>
<div class="wk-paper-list">
{% for paper in section.papers %}
<article class="wk-paper" data-area="{{ paper.area | default: 'finance' }}">
<div>
<h3 class="wk-paper-title">{{ paper.title }}</h3>
<p class="wk-paper-authors">{{ paper.authors }}</p>
{% if paper.journal %}
<p class="wk-paper-venue">
{{ paper.journal }}
{% if paper.volume %}, {{ paper.volume }}{% endif %}
{% if paper.article %}, {{ paper.article }}{% endif %}
{% if paper.year %}&middot; {{ paper.year }}{% endif %}
</p>
{% elsif paper.status %}
<p class="wk-paper-venue">{{ paper.status }}</p>
{% endif %}
<div class="wk-paper-links">
{% if paper.publisher_url %}<a href="{{ paper.publisher_url }}" target="_blank" rel="noopener noreferrer">Publisher</a>{% endif %}
{% if paper.ssrn_url %}<a href="{{ paper.ssrn_url }}" target="_blank" rel="noopener noreferrer">SSRN</a>{% endif %}
{% if paper.abstract or paper.abstract_excerpt %}
<button
                    class="wk-abstract-toggle"
                    type="button"
                    aria-expanded="false"
                    aria-controls="{{ section.id }}-abstract-{{ forloop.index }}"
                  >
Abstract <span class="wk-abstract-chevron" aria-hidden="true">&#9662;</span>
</button>
{% elsif paper.abstract_url %}
<a href="{{ paper.abstract_url }}" target="_blank" rel="noopener noreferrer">Abstract</a>
{% endif %}
</div>
{% if paper.abstract or paper.abstract_excerpt %}
<div class="wk-paper-abstract" id="{{ section.id }}-abstract-{{ forloop.index }}" hidden>
<p>
{% if paper.abstract %}{{ paper.abstract }}{% else %}{{ paper.abstract_excerpt }}{% endif %}
{% if paper.abstract_url %}
<a href="{{ paper.abstract_url }}" target="_blank" rel="noopener noreferrer">Read the full official abstract.</a>
{% endif %}
</p>
</div>
{% endif %}
{% if paper.note and paper.note != "" %}<p class="wk-paper-note">{{ paper.note }}</p>{% endif %}
</div>
</article>
{% endfor %}
</div>
<p class="wk-empty" hidden>{{ section.empty_message }}</p>
</section>
{% endfor %}

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
