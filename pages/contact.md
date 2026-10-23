---
layout: page
title: "Contact"
permalink: /contact/
header: false
show_meta: false
style: |
  .biomotive-contact-form {
    margin-top: 28px;
  }
  .biomotive-contact-form label {
    display: block;
    margin-bottom: 6px;
    font-weight: bold;
    color: #13355F;
  }
  .biomotive-contact-form input,
  .biomotive-contact-form textarea {
    width: 100%;
    box-sizing: border-box;
    font: inherit;
    padding: 12px;
    border: 1px solid #ccd5dd;
    border-radius: 4px;
  }
  .biomotive-contact-form textarea {
    min-height: 180px;
    resize: vertical;
  }
  .biomotive-contact-form button {
    background: #13355F;
    color: white;
    border: 0;
    border-radius: 4px;
    padding: 12px 24px;
    font: inherit;
    cursor: pointer;
  }
  .biomotive-contact-form button:hover {
    background: #244f78;
  }
---

<p>
  Interested in BioMotive, our research or opportunities to collaborate?
  Get in touch with the team at UMC Utrecht and the University of Twente
  using the form below.
</p>

<form
  class="biomotive-contact-form"
  name="biomotive-contact"
  method="POST"
  action="{{ '/contact/thank-you/' | relative_url }}"
  data-netlify="true"
  netlify-honeypot="bot-field"
>
  <input type="hidden" name="form-name" value="biomotive-contact">

  <p hidden>
    <label>
      Leave this field empty:
      <input name="bot-field" tabindex="-1" autocomplete="off">
    </label>
  </p>

  <p>
    <label for="contact-name">Name</label>
    <input
      id="contact-name"
      name="name"
      type="text"
      autocomplete="name"
      required
    >
  </p>

  <p>
    <label for="contact-email">Email address</label>
    <input
      id="contact-email"
      name="email"
      type="email"
      autocomplete="email"
      required
    >
  </p>

  <p>
    <label for="contact-organisation">Organisation (optional)</label>
    <input
      id="contact-organisation"
      name="organisation"
      type="text"
      autocomplete="organization"
    >
  </p>

  <p>
    <label for="contact-message">Message</label>
    <textarea
      id="contact-message"
      name="message"
      rows="7"
      required
    ></textarea>
  </p>

  <button type="submit">Send message</button>
</form>