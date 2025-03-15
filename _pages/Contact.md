---
layout: page
title: Contact
permalink: /Contact/
---

## Form from formspree to get in touch.  

Hi there, Please send you message through here. 

<!-- copied from formspree -->

<form id="contact-form" action="https://formspree.io/f/manennlq" method="POST">
  <p>
  <label>
    Your Email:
    <input type="email" name="email" required>
  </label>
</p>

<p>
  <label>
    Your Message:
    <textarea name="message" required></textarea>
  </label>
  </p>

<p>
  <button type="submit">Send</button>
  <p id="form-status" style="display: none; color: green;">Message sent! I'll get back to you as soon as possible.</p>
</form>
</p>

<script>
  document.getElementById("contact-form").addEventListener("submit", async function(event) {
    event.preventDefault();
    
    let form = event.target;
    let status = document.getElementById("form-status");
    let data = new FormData(form);

    try {
      let response = await fetch(form.action, {
        method: "POST",
        body: data,
        headers: { 'Accept': 'application/json' }
      });

      if (response.ok) {
        status.style.display = "block";
        form.reset();
      } else {
        alert("Sorry! Something went wrong. Please try again.");
      }
    } catch (error) {
      alert("Error submitting the form. Can you try again.");
    }
  });
</script>
