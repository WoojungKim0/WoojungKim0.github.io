---
layout: default
title: Home
permalink: /
nav: false
nav_order: 1
---

<style>
  .wk-home {
    padding: 3.4rem 0 4.75rem;
  }

  .wk-hero {
    display: grid;
    grid-template-columns: minmax(210px, 255px) minmax(0, 1fr);
    gap: clamp(3rem, 6.5vw, 4.2rem);
    align-items: stretch;
  }

  .wk-photo {
    position: relative;
    min-height: 382px;
  }

  .wk-photo img {
    position: absolute;
    inset: 0;
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    border: 1px solid var(--global-divider-color);
    border-radius: 6px;
    box-shadow: 0 2px 6px rgba(23, 27, 31, 0.12);
  }

  .wk-intro {
    display: flex;
    flex-direction: column;
    align-items: stretch;
    min-height: 382px;
    padding: 0;
  }

  .wk-intro > * {
    box-sizing: border-box;
    width: 100%;
    margin-left: 0;
  }

  .wk-name {
    margin: 0 0 0.45rem;
    color: var(--global-text-color);
    font-size: 2rem;
    font-weight: 500;
    letter-spacing: -0.025em;
    line-height: 1.05;
  }

  .wk-position {
    margin: 0;
    color: #4d5358;
    font-size: 1rem;
    font-weight: 300;
    letter-spacing: -0.018em;
  }

  .wk-position-separator {
    padding: 0 0.35rem;
    color: var(--global-text-color-light);
  }

  .wk-affiliation {
    margin: 0.28rem 0 0;
    color: var(--global-text-color-light);
    font-size: 0.84rem;
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
    margin: 1.45rem 0 0;
    color: #41474c;
    font-size: 0.86rem;
    font-weight: 300;
    line-height: 1.7;
  }

  .wk-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
    margin-top: 0.95rem;
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

  .wk-hero-interests {
    margin-top: 1.1rem;
    padding: 0.9rem 1rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 7px;
  }

  .wk-hero-interests h2 {
    margin: 0 0 0.55rem;
    font-size: 0.86rem;
    font-weight: 500;
    letter-spacing: -0.018em;
  }

  .wk-interest-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.18rem 0;
  }

  .wk-interest {
    color: #4d5358;
    font-size: 0.78rem;
    font-weight: 300;
    line-height: 1.45;
  }

  .wk-interest + .wk-interest::before {
    padding: 0 0.55rem;
    color: #a5a9ad;
    content: "·";
  }

  .wk-details {
    margin-top: 4rem;
  }

  .wk-card {
    scroll-margin-top: 5rem;
  }

  .wk-card + .wk-card {
    margin-top: 1rem;
  }

  .wk-card h2 {
    margin: 0 0 0.9rem;
    font-size: 1.02rem;
    font-weight: 400;
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
    font-size: 0.76rem;
  }

  .wk-row-title {
    margin-bottom: 0.08rem;
    font-size: 0.89rem;
    font-weight: 500;
  }

  .wk-row-subtitle {
    color: var(--global-text-color-light);
    font-size: 0.82rem;
    font-weight: 300;
  }

  @media (max-width: 720px) {
    .wk-home {
      padding-top: 2.2rem;
    }

    .wk-hero {
      grid-template-columns: 1fr;
      gap: 1.8rem;
    }

    .wk-photo {
      width: min(220px, 68vw);
      min-height: 0;
    }

    .wk-photo img {
      position: static;
      height: auto;
      aspect-ratio: 2 / 3;
    }

    .wk-intro {
      min-height: 0;
    }

    .wk-position-separator {
      display: block;
      height: 0;
      overflow: hidden;
    }

    .wk-details {
      margin-top: 3rem;
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
          <a class="wk-icon-link" href="{{ site.data.home.links.ssrn }}" target="_blank" rel="noopener noreferrer" title="SSRN" aria-label="SSRN">
            <i class="fa-solid fa-file-lines"></i>
          </a>
        {% endif %}
      </div>

      <section class="wk-hero-interests">
        <h2>Research Interests</h2>
        <div class="wk-interest-list">
          {% for interest in site.data.home.research_interests %}<span class="wk-interest">{{ interest }}</span>{% endfor %}
        </div>
      </section>

    </div>

  </section>

  <div class="wk-details">
    {% for section in site.data.home.detail_sections %}
      {% if section.items.size > 0 %}
        <section class="wk-section-card wk-card">
          <h2>{{ section.title }}</h2>
          {% for item in section.items %}
            <div class="wk-row">
              <div class="wk-period">{{ item.period }}</div>
              <div>
                <div class="wk-row-title">
                  {% if item.url and item.url != "" %}
                    <a href="{{ item.url }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>
                  {% else %}
                    {{ item.title }}
                  {% endif %}
                </div>
                <div class="wk-row-subtitle">{{ item.organization }}</div>
                {% if item.detail and item.detail != "" %}<div class="wk-row-detail">{{ item.detail }}</div>{% endif %}
              </div>
            </div>
          {% endfor %}
        </section>
      {% endif %}
    {% endfor %}

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
