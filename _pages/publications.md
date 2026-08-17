---
layout: page
title: Research
permalink: /research/
description: Research and publications.
nav: true
nav_order: 2
---

<style>
  .wk-research-filter {
    display: flex;
    gap: 0.55rem;
    flex-wrap: wrap;
    margin: 0.4rem 0 2.3rem;
  }

  .wk-filter-btn {
    appearance: none;
    border: 1px solid var(--global-divider-color, #e5e7eb);
    background: var(--global-bg-color, #ffffff);
    color: var(--global-text-color, #1f2937);
    border-radius: 999px;
    padding: 0.48rem 1rem;
    font-size: 0.92rem;
    cursor: pointer;
    transition: all 0.16s ease;
  }

  .wk-filter-btn:hover {
    border-color: var(--global-theme-color, #2563eb);
    color: var(--global-theme-color, #2563eb);
  }

  .wk-filter-btn.active {
    background: var(--global-theme-color, #2563eb);
    border-color: var(--global-theme-color, #2563eb);
    color: #ffffff;
  }

  .wk-research-block {
    margin-bottom: 3rem;
  }

  .wk-research-block h2 {
    font-size: 1.35rem;
    font-weight: 650;
    margin-bottom: 1.3rem;
    padding-bottom: 0.55rem;
    border-bottom: 1px solid var(--global-divider-color, #e5e7eb);
  }
</style>


<div class="wk-research-filter" role="tablist">

  <button
    class="wk-filter-btn active"
    data-filter="all"
    type="button"
  >
    All
  </button>

  <button
    class="wk-filter-btn"
    data-filter="finance"
    type="button"
  >
    Finance
  </button>

  <button
    class="wk-filter-btn"
    data-filter="engineering"
    type="button"
  >
    Engineering
  </button>

</div>


<div id="wk-research-view"></div>


<template id="wk-research-all">

  <section class="wk-research-block">
    <h2>Published Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=published] %}
    </div>
  </section>

  <section class="wk-research-block">
    <h2>Working Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=working] %}
    </div>
  </section>

</template>


<template id="wk-research-finance">

  <section class="wk-research-block">
    <h2>Published Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=published&&area=finance] %}
    </div>
  </section>

  <section class="wk-research-block">
    <h2>Working Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=working&&area=finance] %}
    </div>
  </section>

</template>


<template id="wk-research-engineering">

  <section class="wk-research-block">
    <h2>Published Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=published&&area=engineering] %}
    </div>
  </section>

  <section class="wk-research-block">
    <h2>Working Papers</h2>

    <div class="publications">
      {% bibliography --query @*[status=working&&area=engineering] %}
    </div>
  </section>

</template>


<script>
  (function () {
    function initResearchFilter() {
      const target = document.getElementById("wk-research-view");
      const buttons = document.querySelectorAll(".wk-filter-btn");

      function render(filter) {
        const template = document.getElementById(
          "wk-research-" + filter
        );

        target.replaceChildren(
          template.content.cloneNode(true)
        );

        buttons.forEach((button) => {
          button.classList.toggle(
            "active",
            button.dataset.filter === filter
          );
        });
      }

      buttons.forEach((button) => {
        button.addEventListener("click", function () {
          render(this.dataset.filter);
        });
      });

      render("all");
    }

    if (document.readyState === "loading") {
      document.addEventListener(
        "DOMContentLoaded",
        initResearchFilter
      );
    } else {
      initResearchFilter();
    }
  })();
</script>
