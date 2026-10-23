---
layout: default
title: "Research"
permalink: /research/
header: false
style: |
  .biomotive-research {
    max-width: 1100px;
    margin: 40px auto 64px;
    padding: 0 24px;
  }
  .biomotive-research h1,
  .biomotive-research h2 {
    font-family: "Lato", sans-serif;
    color: #13355F;
  }
  .biomotive-research-intro {
    max-width: 800px;
    margin-bottom: 32px;
    font-size: 18px;
    line-height: 1.7;
  }
  .biomotive-topic-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 24px;
  }
  .biomotive-topic {
    display: flex;
    flex-direction: column;
    padding: 28px;
    background: #fff;
    border: 1px solid #dce3e9;
    border-radius: 8px;
  }
  .biomotive-topic-icon {
    color: #D1822E;
    margin-bottom: 18px;
  }
  .biomotive-topic-icon svg {
    display: block;
    width: 44px;
    height: 44px;
  }
  .biomotive-topic h2 {
    margin: 0 0 16px;
    font-size: 24px;
    line-height: 1.3;
  }
  .biomotive-topic-description {
    line-height: 1.7;
    margin-bottom: 24px;
  }
  .biomotive-topic-team {
    margin-top: auto;
    padding-top: 18px;
    border-top: 1px solid #e5e9ed;
  }
  .biomotive-topic-team-label {
    font-size: 14px;
    font-weight: bold;
    color: #596b79;
    margin: 0 0 12px;
  }
  .biomotive-topic-members {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  .biomotive-topic-member {
    width: 72px;
    text-align: center;
  }
  .biomotive-topic-member a {
    display: block;
    color: #13355F;
  }
  .biomotive-topic-member a:hover,
  .biomotive-topic-member a:focus {
    text-decoration: underline;
  }
  .biomotive-topic-avatar {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 60px;
    height: 60px;
    margin: 0 auto 7px;
    border-radius: 50%;
    overflow: hidden;
    background: #eef2f5;
    color: #596b79;
  }
  .biomotive-topic-avatar img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
  }
  .biomotive-topic-member-name {
    display: block;
    font-size: 12px;
    line-height: 1.35;
  }
  .biomotive-topic-pending {
    margin: 0;
    font-size: 14px;
    color: #596b79;
  }
  @media (max-width: 900px) {
    .biomotive-topic-grid {
      grid-template-columns: 1fr;
    }
  }
---

<main class="biomotive-research">
  <h1>Research</h1>

  <p class="biomotive-research-intro">
    BioMotive focuses on three research themes, connecting
    MRI technology with questions about the human body
    in motion.
  </p>

  <div class="biomotive-topic-grid">
    {% for topic in site.data.research %}
      <article class="biomotive-topic">

        <div class="biomotive-topic-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24"
               fill="none"
               stroke="currentColor"
               stroke-width="1.6"
               stroke-linecap="round"
               stroke-linejoin="round">

            {% case topic.icon %}
              {% when "heart" %}
                <path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.7l-1.1-1.1a5.5 5.5 0 0 0-7.8 7.8L12 21l8.8-8.6a5.5 5.5 0 0 0 0-7.8Z"/>
                <path d="M3 12h4l2-4 4 8 2-4h6"/>

              {% when "movement" %}
                <circle cx="15" cy="4" r="2"/>
                <path d="m12 8 3 3 5 1"/>
                <path d="m12 8-4 4-4 1"/>
                <path d="m12 8-2 7 5 3 1 4"/>
                <path d="m10 15-4 6H2"/>

              {% when "metabolism" %}
                <circle cx="12" cy="12" r="3"/>
                <circle cx="5" cy="5" r="2"/>
                <circle cx="20" cy="7" r="2"/>
                <circle cx="6" cy="20" r="2"/>
                <circle cx="20" cy="19" r="2"/>
                <path d="m6.5 6.5 3.4 3.4"/>
                <path d="m14.6 10.4 3.7-2.3"/>
                <path d="m10.2 14.4-3 4"/>
                <path d="m14.3 14 4.2 3.7"/>
            {% endcase %}

          </svg>
        </div>

        <h2>{{ topic.title | escape }}</h2>
        <p class="biomotive-topic-description">
          {{ topic.description | escape }}
        </p>
        <p>
          <a href="{{ topic.url | relative_url }}"
            aria-label="Read more about {{ topic.title | escape }}">
            Read more &rarr;
          </a>
        </p>

        <div class="biomotive-topic-team">
          <p class="biomotive-topic-team-label">People involved</p>

          {% if topic.members.size > 0 %}
            <ul class="biomotive-topic-members">
              {% for member_id in topic.members %}

                {% assign member_url = '/people/' | append: member_id | append: '/' %}
                {% assign person = site.people | where: "url", member_url | first %}

                {% if person %}
                  <li class="biomotive-topic-member">
                    <a href="{{ person.url | relative_url }}"
                       title="{{ person.title | escape }}">

                      <span class="biomotive-topic-avatar">
                        {% if person.photo and person.photo != "" %}
                          <img
                            src="{{ person.photo | relative_url }}"
                            alt=""
                            loading="lazy"
                          >
                        {% else %}
                          <span aria-hidden="true">
                            {{ person.title | slice: 0, 1 }}
                          </span>
                        {% endif %}
                      </span>

                      <span class="biomotive-topic-member-name">
                        {{ person.title | escape }}
                      </span>
                    </a>
                  </li>
                {% endif %}

              {% endfor %}
            </ul>
          {% else %}
            <p class="biomotive-topic-pending">
              Team information will be added soon.
            </p>
          {% endif %}
        </div>

      </article>
    {% endfor %}
  </div>
</main>