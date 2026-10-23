---
layout: default
title: "Facilities"
permalink: /facilities/
header: false
style: |
  .biomotive-facilities {
    max-width: 1100px;
    margin: 40px auto 64px;
    padding: 0 24px;
  }
  .biomotive-facilities h1,
  .biomotive-facilities h2 {
    font-family: Lato, sans-serif;
    color: #13355F;
  }
  .facility-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 32px;
    margin-top: 32px;
  }
  .facility-card {
    display: block;
    padding: 24px;
    border: 1px solid #dce3e9;
    border-radius: 8px;
    color: #333;
    background: white;
    text-align: center;
    text-decoration: none;
  }
  .facility-card:hover,
  .facility-card:focus-visible {
    border-color: #13355F;
    box-shadow: 0 4px 16px rgba(21, 59, 96, 0.12);
    color: #333;
    text-decoration: none;
  }
  .facility-card img {
    display: block;
    width: 100%;
    height: 300px;
    object-fit: contain;
    margin-bottom: 24px;
  }
  .facility-card h2 {
    font-size: 24px;
    margin: 0 0 8px;
  }
  .facility-card p {
    margin: 0 0 16px;
  }
  .facility-more {
    color: #13355F;
    font-weight: bold;
  }
  @media (max-width: 700px) {
    .facility-grid {
      grid-template-columns: 1fr;
    }
    .facility-card img {
      height: 250px;
    }
  }
---

<main class="biomotive-facilities">
  <h1>Facilities</h1>

  <p>
    BioMotive is developing two complementary MRI facilities to study
    the human body in different positions, under load and during movement.
  </p>

  <div class="facility-grid">
    <a class="facility-card"
       href="{{ '/facilities/paramed/' | relative_url }}">
      <img
        src="{{ '/assets/images/ParamedMRI.jpg' | relative_url }}"
        alt="Paramed upright MRI scanner"
      >
      <h2>0.5T upright MRI</h2>
      <p>University of Twente</p>
      <span class="facility-more">Read more &rarr;</span>
    </a>

    <a class="facility-card"
       href="{{ '/facilities/walk-in-bore/' | relative_url }}">
      <img
        src="{{ '/assets/images/WalkInBoreMRI.jpg' | relative_url }}"
        alt="Concept illustration of the walk-in-bore MRI scanner"
      >
      <h2>3T walk-in-bore MRI</h2>
      <p>UMC Utrecht</p>
      <span class="facility-more">Read more &rarr;</span>
    </a>
  </div>
</main>