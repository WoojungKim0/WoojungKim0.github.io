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
    counter-reset: paper;
    padding-top: 0.5rem;
  }

  .wk-research-intro {
    max-width: 720px;
    margin: 0 0 3.25rem;
    color: var(--global-text-color-light);
    font-size: 0.86rem;
    font-weight: 300;
    line-height: 1.7;
  }

  .wk-research-section {
    margin-bottom: 3.75rem;
  }

  .wk-research-section h2 {
    margin: 0 0 1.65rem;
    color: var(--global-text-color);
    font-size: 1.16rem;
    font-weight: 300;
    letter-spacing: -0.03em;
  }

  .wk-paper-list {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
  }

  .wk-paper {
    counter-increment: paper;
    display: grid;
    grid-template-columns: 46px minmax(0, 1fr);
    gap: 0.5rem;
    margin: 0 -0.25rem;
    padding: 0.75rem 0.25rem;
    border-radius: 4px;
    transition: background-color 0.16s ease;
  }

  .wk-paper:hover {
    background: rgba(11, 18, 21, 0.025);
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

  .wk-paper-links a {
    color: var(--global-theme-color);
    text-decoration: none;
    transition:
      color 0.16s ease,
      transform 0.16s ease;
  }

  .wk-paper-links a:hover {
    color: var(--global-hover-color);
    transform: translateY(-1px);
  }

  .wk-paper-links a + a::before {
    content: "·";
    padding: 0 0.55rem;
    color: var(--global-text-color-light);
  }

  @media (max-width: 560px) {
    .wk-research-intro {
      margin-bottom: 2.5rem;
    }

    .wk-paper {
      grid-template-columns: 34px minmax(0, 1fr);
    }
  }
</style>

<div class="wk-research">
  <p class="wk-research-intro">
    My research centers on empirical asset pricing, factor investing, cross-asset predictability, and machine learning applications in financial markets.
  </p>

  {% if site.data.research.published.size > 0 %}
    <section class="wk-research-section">
      <h2>Published Papers</h2>
      <div class="wk-paper-list">
        {% for paper in site.data.research.published %}
          <article class="wk-paper">
            <div>
              <h3 class="wk-paper-title">{{ paper.title }}</h3>
              <p class="wk-paper-authors">{{ paper.authors }}</p>
              <p class="wk-paper-venue">
                {{ paper.journal }}{% if paper.volume %}, {{ paper.volume }}{% endif %}{% if paper.article %}, {{ paper.article }}{% endif %} · {{ paper.year }}
              </p>
              <div class="wk-paper-links">
                {% if paper.publisher_url %}<a href="{{ paper.publisher_url }}" target="_blank" rel="noopener noreferrer">Publisher</a>{% endif %}
                {% if paper.ssrn_url %}<a href="{{ paper.ssrn_url }}" target="_blank" rel="noopener noreferrer">SSRN</a>{% endif %}
              </div>
            </div>
          </article>
        {% endfor %}
      </div>
    </section>
  {% endif %}

  {% if site.data.research.working.size > 0 %}
    <section class="wk-research-section">
      <h2>Working Papers</h2>
      <div class="wk-paper-list">
        {% for paper in site.data.research.working %}
          <article class="wk-paper">
            <div>
              <h3 class="wk-paper-title">{{ paper.title }}</h3>
              <p class="wk-paper-authors">{{ paper.authors }}</p>
              {% if paper.status %}<p class="wk-paper-venue">{{ paper.status }}</p>{% endif %}
              <div class="wk-paper-links">
                {% if paper.ssrn_url %}<a href="{{ paper.ssrn_url }}" target="_blank" rel="noopener noreferrer">SSRN</a>{% endif %}
                {% if paper.publisher_url %}<a href="{{ paper.publisher_url }}" target="_blank" rel="noopener noreferrer">Publisher</a>{% endif %}
              </div>
            </div>
          </article>
        {% endfor %}
      </div>
    </section>
  {% endif %}
</div>
