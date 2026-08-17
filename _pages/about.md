---
layout: default
title: Home
permalink: /
nav: false
nav_order: 1
---

<style>
  .wk-home {
    padding: 3.25rem 0 4.5rem;
  }

  .wk-hero {
    display: grid;
    grid-template-columns: minmax(190px, 238px) minmax(0, 1fr);
    gap: clamp(2.5rem, 6vw, 4.75rem);
    align-items: start;
  }

  .wk-photo img {
    display: block;
    width: 100%;
    aspect-ratio: 4 / 5;
    object-fit: cover;
    border-radius: 5px;
  }

  .wk-name {
    margin: -0.25rem 0 0.4rem;
    color: var(--global-text-color);
    font-size: clamp(2rem, 4vw, 2.45rem);
    font-weight: 500;
    letter-spacing: -0.045em;
    line-height: 1.1;
  }

  .wk-position {
    margin: 0;
    font-size: 1.02rem;
    font-weight: 300;
    letter-spacing: -0.02em;
  }

  .wk-position-separator {
    padding: 0 0.35rem;
    color: var(--global-text-color-light);
  }

  .wk-affiliation {
    margin: 0.2rem 0 0;
    color: var(--global-text-color-light);
    font-size: 0.86rem;
  }

  .wk-email {
    display: inline-block;
    margin-top: 0.18rem;
    color: var(--global-theme-color);
    font-size: 0.82rem;
    font-weight: 300;
    text-decoration: none;
  }

  .wk-email:hover {
    color: var(--global-hover-color);
  }

  .wk-bio {
    max-width: 680px;
    margin: 1.55rem 0 0;
    font-size: 0.88rem;
    font-weight: 300;
    line-height: 1.72;
  }

  .wk-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
    margin-top: 1rem;
  }

  .wk-icon-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    color: var(--global-theme-color);
    text-decoration: none !important;
    transition:
      color 0.16s ease,
      transform 0.16s ease;
  }

  .wk-icon-link:hover {
    color: var(--global-hover-color);
    transform: translateY(-1px);
  }

  .wk-icon-link i {
    font-size: 1rem;
  }

  .wk-interest-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
  }

  .wk-interest {
    padding: 0.38rem 0.72rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 999px;
    color: var(--global-text-color);
    font-size: 0.78rem;
    font-weight: 300;
    line-height: 1.25;
  }

  .wk-details {
    margin-top: 3.5rem;
  }

  .wk-card {
    padding: 1.45rem 1.6rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 9px;
    background: var(--wk-panel-bg-color);
    box-shadow: var(--wk-panel-shadow);
  }

  .wk-card + .wk-card {
    margin-top: 1rem;
  }

  .wk-card h2 {
    margin: 0 0 1rem;
    font-size: 0.98rem;
    font-weight: 500;
    letter-spacing: -0.025em;
  }

  .wk-row {
    display: grid;
    grid-template-columns: 125px minmax(0, 1fr);
    gap: 1rem;
    padding: 0.85rem 0;
  }

  .wk-row + .wk-row {
    border-top: 1px solid var(--global-divider-color);
  }

  .wk-period,
  .wk-row-detail {
    color: var(--global-text-color-light);
    font-size: 0.78rem;
  }

  .wk-row-title {
    margin-bottom: 0.08rem;
    font-size: 0.91rem;
    font-weight: 500;
  }

  .wk-row-subtitle {
    font-size: 0.84rem;
    font-weight: 300;
  }

  @media (max-width: 720px) {
    .wk-home {
      padding-top: 1.8rem;
    }

    .wk-hero {
      grid-template-columns: 1fr;
      gap: 1.8rem;
    }

    .wk-photo {
      width: min(210px, 68vw);
    }

    .wk-position-separator {
      display: block;
      height: 0;
      overflow: hidden;
    }

    .wk-details {
      margin-top: 2.75rem;
    }

    .wk-card {
      padding: 1.2rem;
    }

    .wk-row {
      grid-template-columns: 1fr;
      gap: 0.22rem;
    }
  }
</style>

<div class="wk-home">
  <section class="wk-hero">
    <div class="wk-photo">
      <img src="{{ '/assets/img/prof_pic.jpg' | relative_url | bust_file_cache }}" alt="{{ site.data.home.name }}">
    </div>

    <div class="wk-intro">
      <h1 class="wk-name">{{ site.data.home.name }}</h1>
      <p class="wk-position">
        {{ site.data.home.position }}<span class="wk-position-separator" aria-hidden="true">·</span>{{ site.data.home.research_focus }}
      </p>
      <p class="wk-affiliation">{{ site.data.home.affiliation }}</p>
      <a class="wk-email" href="mailto:{{ site.data.home.links.email }}">{{ site.data.home.links.email }}</a>

      <p class="wk-bio">{{ site.data.home.bio }}</p>

      <div class="wk-links" aria-label="Academic and professional profiles">
        {% if site.data.home.links.cv != "" %}
          <a class="wk-icon-link" href="{{ site.data.home.links.cv | relative_url }}" title="Curriculum Vitae" aria-label="Curriculum Vitae">
            <i class="fa-solid fa-file-pdf"></i>
          </a>
        {% endif %}
        {% if site.data.home.links.scholar != "" %}
          <a class="wk-icon-link" href="{{ site.data.home.links.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar" aria-label="Google Scholar">
            <i class="ai ai-google-scholar"></i>
          </a>
        {% endif %}
        {% if site.data.home.links.linkedin != "" %}
          <a class="wk-icon-link" href="{{ site.data.home.links.linkedin }}" target="_blank" rel="noopener noreferrer" title="LinkedIn" aria-label="LinkedIn">
            <i class="fa-brands fa-linkedin-in"></i>
          </a>
        {% endif %}
        {% if site.data.home.links.ssrn != "" %}
          <a class="wk-icon-link" href="{{ site.data.home.links.ssrn }}" target="_blank" rel="noopener noreferrer" title="SSRN" aria-label="SSRN">
            <i class="fa-solid fa-file-lines"></i>
          </a>
        {% endif %}
      </div>

    </div>
  </section>

  <div class="wk-details">
    <section class="wk-card">
      <h2>Research Interests</h2>
      <div class="wk-interest-list">
        {% for interest in site.data.home.research_interests %}<span class="wk-interest">{{ interest }}</span>{% endfor %}
      </div>
    </section>

    <section class="wk-card">
      <h2>Education</h2>
      {% for item in site.data.home.education %}
        <div class="wk-row">
          <div class="wk-period">{{ item.period }}</div>
          <div>
            <div class="wk-row-title">{{ item.degree }}</div>
            <div class="wk-row-subtitle">{{ item.institution }}</div>
            {% if item.detail and item.detail != "" %}<div class="wk-row-detail">{{ item.detail }}</div>{% endif %}
          </div>
        </div>
      {% endfor %}
    </section>

    {% if site.data.home.work_experience.size > 0 %}
      <section class="wk-card">
        <h2>Experience</h2>
        {% for item in site.data.home.work_experience %}
          <div class="wk-row">
            <div class="wk-period">{{ item.period }}</div>
            <div>
              <div class="wk-row-title">{{ item.position }}</div>
              <div class="wk-row-subtitle">{{ item.institution }}</div>
              {% if item.detail and item.detail != "" %}<div class="wk-row-detail">{{ item.detail }}</div>{% endif %}
            </div>
          </div>
        {% endfor %}
      </section>
    {% endif %}
  </div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const navContainer =
      document.querySelector("nav.navbar .container") || document.querySelector("header nav .container") || document.querySelector("nav .container");

    if (navContainer && !navContainer.querySelector(".navbar-brand")) {
      const brand = document.createElement("a");
      brand.className = "navbar-brand wk-navbar-brand";
      brand.href = "{{ '/' | relative_url }}";
      brand.textContent = "Woojung Kim";
      navContainer.prepend(brand);
    }
  });
</script>
