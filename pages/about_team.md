---
layout: default
title: "People"
permalink: /about/team/
header: false
style: |
  .biomotive-people {
    max-width: 1100px;
    margin: 40px auto 64px;
    padding: 0 24px;
  }
  .biomotive-people h1,
  .biomotive-people h2 {
    font-family: "Lato", sans-serif;
    color: #153b60;
  }
  .biomotive-people-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 40px 32px;
    margin-top: 32px;
  }
  .biomotive-person {
    text-align: center;
  }
  .biomotive-person-photo {
    display: block;
    aspect-ratio: 1 / 1;
    overflow: hidden;
    background: #eef2f5;
  }
  .biomotive-person-photo img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
  .biomotive-person-placeholder {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    color: #596b79;
    font-size: 15px;
  }
  .biomotive-person h2 {
    font-size: 21px;
    margin: 16px 0 6px;
  }
  .biomotive-person h2 a {
    color: inherit;
  }
  .biomotive-person a:hover,
  .biomotive-person a:focus {
    text-decoration: underline;
  }
  .biomotive-person p {
    margin: 0;
    color: #596b79;
  }
  @media (max-width: 800px) {
    .biomotive-people-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }
  @media (max-width: 480px) {
    .biomotive-people-grid {
      grid-template-columns: 1fr;
    }
  }
---

<main class="biomotive-people">
  <h1>People</h1>

  <p>
    Meet the people involved in BioMotive.
    Select a name to learn more about their work and role
    within the project.
  </p>

  <div class="biomotive-people-grid">

    {% assign members = site.people | sort: "order" %}

    {% for person in members %}
      <article class="biomotive-person">

        <a class="biomotive-person-photo"
           href="{{ person.url | relative_url }}"
           aria-label="View profile of {{ person.title | escape }}">

          {% if person.photo and person.photo != "" %}
            <img
              src="{{ person.photo | relative_url }}"
              alt="{{ person.title | escape }}"
              loading="lazy"
            >
          {% else %}
            <span class="biomotive-person-placeholder">
              Photo to follow
            </span>
          {% endif %}

        </a>

        <h2>
          <a href="{{ person.url | relative_url }}">
            {{ person.title }}
          </a>
        </h2>

        <p>{{ person.role }}</p>

      </article>
    {% endfor %}

  </div>
</main>