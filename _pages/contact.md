---
title: "Contact"
permalink: /contact/
header:
  overlay_image: images/2contact.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  actions:
    - label: "Book Now!"
      url: "#form" # Link to a form section instead of mailto link
---

## Enquiring and booking is as simple as contacting us:

<br>

<i class="fas fa-envelope-square"></i> **Fill out the form below to reach us:**

<!-- The updated form with an anchor to scroll here -->
<a id="form"></a>
<form
  action="https://formspree.io/f/xannrwpb"
  method="POST"
>
  <label>
    Your email:
    <input type="email" name="email" required>
  </label>
  <label>
    Your message:
    <textarea name="message" required></textarea>
  </label>
  <!-- Additional fields or customization can be added here -->
  <button type="submit">Send</button>
</form>
