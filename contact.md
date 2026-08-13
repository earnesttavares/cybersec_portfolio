---
title: Contact
nav_order: 6
--- 

<div class="contact-box">
  <h2>Contact Me</h2>
  <p>Feel free to send a message using the form below:</p>

  <form action="https://formspree.io/f/mrpzkajv" method="POST" class="contact-form">
    <label>
      Your Name:
      <input type="text" name="name" required>
    </label>

    <label>
      Your Email:
      <input type="email" name="email" required>
    </label>

    <label>
      Message:
      <textarea name="message" rows="5" required></textarea>
    </label>

    <button type="submit">Send Message</button>
  </form>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const form = document.querySelector(".contact-form");
  const successBox = document.getElementById("success-message");

  form.addEventListener("submit", async function (event) {
    event.preventDefault(); // stop default redirect

    const formData = new FormData(form);

    // Send to Formspree
    const response = await fetch(form.action, {
      method: "POST",
      body: formData,
      headers: { "Accept": "application/json" }
    });

    if (response.ok) {
      form.reset();                 // clear fields
      successBox.style.display = "block"; // show success message
    } else {
      alert("There was an issue sending your message. Please try again.");
    }
  });
});
</script>
