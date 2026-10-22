---
layout: default
title: "BioMotive"
permalink: /
header: false
style: |
  .biomotive-home {
    max-width: 1100px;
    margin: 36px auto 64px;
    padding: 0 24px;
  }
  .biomotive-hero {
    margin: 0 0 36px;
  }
  .biomotive-hero img {
    display: block;
    width: 100%;
    height: auto;
    margin: 0 auto;
  }
  .biomotive-home figcaption {
    margin-top: 8px;
    font-size: 13px;
    color: #666;
  }
  .biomotive-home h1,
  .biomotive-home h2,
  .biomotive-home h3 {
    font-family: "Lato", sans-serif;
    color: #153b60;
  }
  .biomotive-about {
    margin-bottom: 44px;
  }
  .biomotive-about p {
    font-size: 18px;
    line-height: 1.7;
  }
  .biomotive-news-item {
    display: grid;
    grid-template-columns: 260px minmax(0, 1fr);
    gap: 28px;
    padding: 26px 0;
    border-top: 1px solid #ddd;
  }
  .biomotive-news-item img {
    display: block;
    width: 100%;
    height: auto;
  }
  .biomotive-news-item time {
    display: block;
    color: #666;
    font-size: 14px;
    margin-bottom: 8px;
  }
  .biomotive-news-item h3 {
    font-size: 24px;
    margin: 0 0 12px;
  }
  .biomotive-news-item h3 a {
    color: inherit;
  }
  .biomotive-news-item p {
    margin-bottom: 12px;
  }
  .biomotive-read-more {
    font-weight: bold;
  }
  @media (max-width: 640px) {
    .biomotive-news-item {
      grid-template-columns: 1fr;
      gap: 18px;
    }
  }
---

<main class="biomotive-home">

  <figure class="biomotive-hero">
    <img
      src="{{ '/assets/images/MainPage.png' | relative_url }}"
      alt="BioMotive — imaging the biomechanics of the internal human body in motion"
      width="1280"
      height="720"
    >
    <figcaption>
      Concept illustration of the BioMotive vision.
    </figcaption>
  </figure>

  <section class="biomotive-about" aria-labelledby="about-title">
    <h1 id="about-title">About BioMotive</h1>
    <p>
      BioMotive is developing MRI research facilities to study
      the human body in motion. With facilities at UMC Utrecht
      and the University of Twente, the consortium aims to
      reveal how movement and posture affect muscles, organs
      and metabolism.
    </p>
  </section>

  <section aria-labelledby="news-title">
  <h2 id="news-title">News</h2>

  {% for post in site.categories.news %}
    <article class="biomotive-news-item">

      <a href="{{ post.url | relative_url }}"
         aria-label="{{ post.title | escape }}">
        <img
          src="{{ post.news_image | relative_url }}"
          alt="{{ post.news_image_alt | escape }}"
          loading="lazy"
        >
      </a>

      <div>
        <time datetime="{{ post.date | date: '%Y-%m-%d' }}">
          {{ post.date | date: "%-d %B %Y" }}
        </time>

        <h3>
          <a href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </h3>

        <p>{{ post.summary | escape }}</p>

        <a class="biomotive-read-more"
           href="{{ post.url | relative_url }}">
          Read more &rarr;
        </a>
      </div>

    </article>
  {% else %}
    <p>Project news will appear here soon.</p>
  {% endfor %}
</section>

</main>