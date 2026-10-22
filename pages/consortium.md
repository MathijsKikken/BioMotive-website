---
layout: default
title: "Consortium"
permalink: /consortium/
header: false
style: |
  .consortium-page { max-width: 1100px; margin: 40px auto 64px; padding: 0 24px; }
  .consortium-page h1, .consortium-page h2 { font-family: Lato, sans-serif; color: #153b60; }
  .consortium-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 24px; margin-top: 32px; }
  .consortium-card { display: flex; flex-direction: column; align-items: center; padding: 24px 16px; border: 1px solid #dce3e9; border-radius: 8px; background: white; text-align: center; color: #153b60; text-decoration: none; }
  .consortium-card:hover, .consortium-card:focus-visible { border-color: #153b60; box-shadow: 0 4px 16px rgba(21,59,96,.12); text-decoration: none; }
  .consortium-logo-frame { height: 100px; width: 100%; display: flex; align-items: center; justify-content: center; }
  .consortium-logo {
    display: block;
    max-width: 100%;
    max-height: 100px;
    width: auto;
    height: auto;
    object-fit: contain;
  }
  .consortium-placeholder { color: #667785; font-size: 14px; }
  .consortium-card h2 { font-size: 19px; margin: 16px 0 12px; }
  .consortium-more { margin-top: auto; font-size: 14px; }
  @media (max-width: 850px) { .consortium-grid { grid-template-columns: repeat(2,minmax(0,1fr)); } }
  @media (max-width: 550px) { .consortium-grid { grid-template-columns: 1fr; } }
---

<main class="consortium-page">
  <h1>Consortium</h1>
  <p>BioMotive brings together partners to develop MRI infrastructure and research into the human body in motion. Select a partner to learn more about their involvement.</p>
  <div class="consortium-grid">
    {% assign partners = site.partners | sort: "order" %}
    {% for partner in partners %}
    <a class="consortium-card" href="{{ partner.url | relative_url }}">
      <div class="consortium-logo-frame" aria-hidden="true">
        {% if partner.logo and partner.logo != "" %}
        <img
          class="consortium-logo"
          src="{{ partner.logo | relative_url }}"
          alt=""
          loading="lazy"
        >
        {% else %}
        <span class="consortium-placeholder">Logo to be added</span>
        {% endif %}
      </div>
      <h2>{{ partner.title | escape }}</h2>
      <span class="consortium-more">Read more &rarr;</span>
    </a>
    {% endfor %}
  </div>
  <p style="margin-top: 32px;">BioMotive is funded by NWO.</p>
</main>
