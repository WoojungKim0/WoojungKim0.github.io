---
layout: default
title: Home
permalink: /
nav: true
nav_order: 1
---

<style>
  .wk-home {
    padding: 2.5rem 0 4rem;
  }

  .wk-hero {
    display: grid;
    grid-template-columns: minmax(190px, 235px) minmax(0, 1fr);
    gap: 2.8rem;
    align-items: center;
    margin-bottom: 3.5rem;
  }

  .wk-photo img {
    width: 100%;
    aspect-ratio: 4 / 5;
    object-fit: cover;
    border-radius: 12px;
    border: 1px solid var(--global-divider-color, #e5e7eb);
    box-shadow: 0 8px 28px rgba(0, 0, 0, 0.06);
  }

  .wk-name {
    margin: 0 0 0.4rem;
    font-size: clamp(2.1rem, 4vw, 3rem);
    line-height: 1.1;
    font-weight: 650;
    letter-spacing: -0.035em;
  }

  .wk-position {
    margin: 0;
    font-size: 1.1rem;
    font-weight: 500;
  }

  .wk-affiliation {
    margin: 0.15rem 0 1.2rem;
    color: var(--global-text-color-light, #6b7280);
  }

  .wk-bio {
    max-width: 680px;
    margin: 0 0 1.35rem;
    line-height: 1.72;
  }

  .wk-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 0.65rem;
  }

  .wk-icon-link {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    border: 1px solid var(--global-divider-color, #e5e7eb);
    display: inline-flex;
    align-items: center;
    justify-content: center;
    text-decoration: none !important;
    color: var(--global-text-color, #1f2937);
    background: var(--global-bg-color, #ffffff);
    transition: transform 0.18s ease, border-color 0.18s ease,
      color 0.18s ease;
  }

  .wk-icon-link:hover {
    transform: translateY(-2px);
    border-color: var(--global-theme-color, #2563eb);
    color: var(--global-theme-color, #2563eb);
  }

  .wk-icon-link i {
    font-size: 1.15rem;
  }

  .wk-sections {
    display: grid;
    gap: 1.15rem;
  }

  .wk-card {
    border: 1px solid var(--global-divider-color, #e5e7eb);
    border-radius: 12px;
    padding: 1.45rem 1.6rem;
    background: var(--global-card-bg-color, var(--global-bg-color, #ffffff));
  }

  .wk-card h2 {
    margin: 0 0 1.05rem;
    font-size: 1.2rem;
    font-weight: 650;
    letter-spacing: -0.01em;
  }

  .wk-interest-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
  }

  .wk-interest {
    display: inline-block;
    padding: 0.4rem 0.72rem;
    border-radius: 999px;
    border: 1px solid var(--global-divider-color, #e5e7eb);
    font-size: 0.93rem;
  }

  .wk-row {
    display: grid;
    grid-template-columns: 125px minmax(0, 1fr);
    gap: 1rem;
    padding: 0.9rem 0;
    border-top: 1px solid var(--global-divider-color, #e5e7eb);
  }

  .wk-row:first-of-type {
    border-top: 0;
    padding-top: 0;
  }

  .wk-row:last-of-type {
    padding-bottom: 0;
  }

  .wk-period {
    font-size: 0.92rem;
    color: var(--global-text-color-light, #6b7280);
  }

  .wk-row-title {
    font-weight: 600;
    margin-bottom: 0.08rem;
  }

  .wk-row-subtitle {
    margin-bottom: 0.12rem;
  }

  .wk-row-detail {
    color: var(--global-text-color-light, #6b7280);
    font-size: 0.93rem;
  }

  @media (max-width: 720px) {
    .wk-home {
      padding-top: 1.3rem;
    }

    .wk-hero {
      grid-template-columns: 1fr;
      gap: 1.5rem;
      text-align: center;
    }

    .wk-photo {
      max-width: 190px;
      margin: 0 auto;
    }

    .wk-bio {
      text-align: left;
      margin-left: auto;
      margin-right: auto;
    }

    .wk-links {
      justify-content: center;
    }

    .wk-row {
      grid-template-columns: 1fr;
      gap: 0.25rem;
    }
  }
</style>

<div class="wk-home">

  <section class="wk-hero">

    <div class="wk-photo">
      <img
        src="{{ '/assets/img/prof_pic.jpg' | relative_url }}"
        alt="{{ site.data.home.name }}"
      >
    </div>

    <div class="wk-intro">

      <h1 class="wk-name">{{ site.data.home.name }}</h1>

      <p class="wk-position">
        {{ site.data.home.position }}
      </p>

      <p class="wk-affiliation">
        {{ site.data.home.affiliation }}
      </p>

      <p class="wk-bio">
        {{ site.data.home.bio }}
      </p>

      <div class="wk-links">

        {% if site.data.home.links.email != "" %}
        <a
          class="wk-icon-link"
          href="mailto:{{ site.data.home.links.email }}"
          title="Email"
          aria-label="Email"
        >
          <i class="fa-solid fa-envelope"></i>
        </a>
        {% endif %}

        {% if site.data.home.links.cv != "" %}
        <a
          class="wk-icon-link"
          href="{{ site.data.home.links.cv | relative_url }}"
          title="Download CV"
          aria-label="Download CV"
          download
        >
          <i class="fa-solid fa-file-pdf"></i>
        </a>
        {% endif %}

        {% if site.data.home.links.scholar != "" %}
        <a
          class="wk-icon-link"
          href="{{ site.data.home.links.scholar }}"
          target="_blank"
          rel="noopener noreferrer"
          title="Google Scholar"
          aria-label="Google Scholar"
        >
          <i class="ai ai-google-scholar"></i>
        </a>
        {% endif %}

        {% if site.data.home.links.linkedin != "" %}
        <a
          class="wk-icon-link"
          href="{{ site.data.home.links.linkedin }}"
          target="_blank"
          rel="noopener noreferrer"
          title="LinkedIn"
          aria-label="LinkedIn"
        >
          <i class="fa-brands fa-linkedin-in"></i>
        </a>
        {% endif %}

        {% if site.data.home.links.ssrn != "" %}
        <a
          class="wk-icon-link"
          href="{{ site.data.home.links.ssrn }}"
          target="_blank"
          rel="noopener noreferrer"
          title="SSRN"
          aria-label="SSRN"
        >
          <i class="fa-solid fa-file-lines"></i>
        </a>
        {% endif %}

      </div>

    </div>

  </section>


  <div class="wk-sections">

    <section class="wk-card">

      <h2>Research Interests</h2>

      <div class="wk-interest-list">

        {% for interest in site.data.home.research_interests %}
          <span class="wk-interest">{{ interest }}</span>
        {% endfor %}

      </div>

    </section>


    <section class="wk-card">

      <h2>Education</h2>

      {% for item in site.data.home.education %}

      <div class="wk-row">

        <div class="wk-period">
          {{ item.period }}
        </div>

        <div>

          <div class="wk-row-title">
            {{ item.degree }}
          </div>

          <div class="wk-row-subtitle">
            {{ item.institution }}
          </div>

          {% if item.detail and item.detail != "" %}
          <div class="wk-row-detail">
            {{ item.detail }}
          </div>
          {% endif %}

        </div>

      </div>

      {% endfor %}

    </section>


    {% if site.data.home.work_experience.size > 0 %}

    <section class="wk-card">

      <h2>Work Experience</h2>

      {% for item in site.data.home.work_experience %}

      <div class="wk-row">

        <div class="wk-period">
          {{ item.period }}
        </div>

        <div>

          <div class="wk-row-title">
            {{ item.position }}
          </div>

          <div class="wk-row-subtitle">
            {{ item.institution }}
          </div>

          {% if item.detail and item.detail != "" %}
          <div class="wk-row-detail">
            {{ item.detail }}
          </div>
          {% endif %}

        </div>

      </div>

      {% endfor %}

    </section>

    {% endif %}

  </div>

</div>
