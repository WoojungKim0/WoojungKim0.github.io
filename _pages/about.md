---
layout: default
title: Home
permalink: /
nav: false
nav_order: 1
---

<style>
  .wk-home {
    padding: 4.15rem 0 5.25rem;
  }

  .wk-hero {
    display: grid;
    grid-template-columns: minmax(200px, 248px) minmax(0, 1fr);
    gap: clamp(2.75rem, 6vw, 5rem);
    align-items: center;
  }

  .wk-photo {
    position: relative;
  }

  .wk-photo::after {
    position: absolute;
    z-index: -1;
    right: -0.75rem;
    bottom: -0.75rem;
    width: 76%;
    height: 76%;
    border-radius: 20px;
    background: color-mix(in srgb, var(--global-theme-color) 10%, transparent);
    content: "";
  }

  .wk-photo img {
    display: block;
    width: 100%;
    aspect-ratio: 4 / 5;
    object-fit: cover;
    border: 1px solid color-mix(in srgb, var(--global-theme-color) 22%, transparent);
    border-radius: 18px;
    box-shadow: 0 24px 54px rgba(32, 67, 94, 0.14);
  }

  .wk-name {
    margin: -0.2rem 0 0.45rem;
    color: var(--global-text-color);
    font-family: "Newsreader", Georgia, serif !important;
    font-size: clamp(2.75rem, 5vw, 3.45rem);
    font-weight: 500;
    letter-spacing: -0.055em;
    line-height: 0.98;
  }

  .wk-position {
    margin: 0;
    color: color-mix(in srgb, var(--global-text-color) 90%, var(--global-theme-color));
    font-size: 1.04rem;
    font-weight: 500;
    letter-spacing: -0.025em;
  }

  .wk-position-separator {
    padding: 0 0.35rem;
    color: var(--global-text-color-light);
  }

  .wk-affiliation {
    margin: 0.32rem 0 0;
    color: var(--global-text-color-light);
    font-size: 0.88rem;
  }

  .wk-email {
    display: inline-block;
    margin-top: 0.22rem;
    color: var(--global-theme-color);
    font-size: 0.84rem;
    font-weight: 500;
    text-decoration: none;
  }

  .wk-email:hover {
    color: var(--global-hover-color);
  }

  .wk-bio {
    max-width: 680px;
    margin: 1.7rem 0 0;
    color: color-mix(in srgb, var(--global-text-color) 88%, transparent);
    font-size: 0.94rem;
    font-weight: 400;
    line-height: 1.78;
  }

  .wk-links {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 0.62rem;
    margin-top: 1.2rem;
  }

  .wk-icon-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 2.15rem;
    height: 2.15rem;
    border: 1px solid var(--wk-panel-border-color);
    border-radius: 50%;
    background: var(--wk-panel-bg-color);
    box-shadow: 0 6px 18px rgba(32, 67, 94, 0.045);
    color: var(--global-theme-color);
    text-decoration: none !important;
    transition:
      color 0.16s ease,
      border-color 0.16s ease,
      background-color 0.16s ease,
      transform 0.16s ease;
  }

  .wk-icon-link:hover {
    color: var(--global-hover-color);
    border-color: color-mix(in srgb, var(--global-theme-color) 38%, transparent);
    background: var(--global-card-bg-color);
    transform: translateY(-2px);
  }

  .wk-icon-link i {
    font-size: 0.92rem;
  }

  .wk-interest-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.58rem;
  }

  .wk-interest {
    padding: 0.43rem 0.78rem;
    border: 1px solid color-mix(in srgb, var(--global-theme-color) 17%, transparent);
    border-radius: 999px;
    background: var(--wk-chip-bg-color);
    color: var(--global-text-color);
    font-size: 0.8rem;
    font-weight: 500;
    line-height: 1.25;
  }

  .wk-details {
    margin-top: 4.25rem;
  }

  .wk-card {
    scroll-margin-top: 5rem;
  }

  .wk-card + .wk-card {
    margin-top: 1.15rem;
  }

  .wk-card h2 {
    margin: 0 0 1.05rem;
    font-family: "Newsreader", Georgia, serif !important;
    font-size: 1.32rem;
    font-weight: 500;
    letter-spacing: -0.035em;
  }

  .wk-row {
    display: grid;
    grid-template-columns: 125px minmax(0, 1fr);
    gap: 1rem;
    padding: 0.92rem 0;
  }

  .wk-row + .wk-row {
    border-top: 1px solid var(--global-divider-color);
  }

  .wk-period,
  .wk-row-detail {
    color: var(--global-text-color-light);
    font-size: 0.8rem;
  }

  .wk-row-title {
    margin-bottom: 0.08rem;
    font-size: 0.94rem;
    font-weight: 600;
  }

  .wk-row-subtitle {
    color: var(--global-text-color-light);
    font-size: 0.86rem;
    font-weight: 400;
  }

  @media (max-width: 720px) {
    .wk-home {
      padding-top: 2.35rem;
    }

    .wk-hero {
      grid-template-columns: 1fr;
      gap: 1.8rem;
    }

    .wk-photo {
      width: min(220px, 68vw);
    }

    .wk-position-separator {
      display: block;
      height: 0;
      overflow: hidden;
    }

    .wk-details {
      margin-top: 3.25rem;
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

    </div>

  </section>

  <div class="wk-details">
    <section class="wk-section-card wk-card">
      <h2>Research Interests</h2>
      <div class="wk-interest-list">
        {% for interest in site.data.home.research_interests %}<span class="wk-interest">{{ interest }}</span>{% endfor %}
      </div>
    </section>

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
