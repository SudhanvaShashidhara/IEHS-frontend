<script>
  export let segment;
  import FaMapMarkerAlt from "svelte-icons/fa/FaMapMarkerAlt.svelte";
</script>

<style>
  footer {
    background-color: var(--main-color);
    color: #fff;
    display: flex;
    flex-direction: column;
  }
  section {
    width: 90%;
    margin: 1rem auto;
  }

  .address,
  .phone,
  .email {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .contact-logo {
    width: 8%;
  }
  .contact-text {
    width: 85%;
  }
  .footer-copyright {
    padding: 0.9rem;
    background-color: var(--main-color-variant);
  }
</style>

<footer>
  <section class="contact-section">
    <div class="address">
      <div class="contact-logo">
        <FaMapMarkerAlt />
      </div>
      <div class="contact-text">
        <a
          href="https://www.google.co.in/maps/place/Ideal+English+High+School/@13.053981,77.514557,15z/data=!4m5!3m4!1s0x0:0x7d5cda0e0881fed1!8m2!3d13.053981!4d77.514557">
          #70-71, 3rd Main, Bhel Mini Colony, T. Dasarahalli, Bhel Mini Colony,
          Jalahalli West, Bengaluru, Karnataka 560057
        </a>
      </div>
    </div>
    <div class="phone">
      <div class="contact-logo">
        <FaMapMarkerAlt />
      </div>
      <div class="contact-text">
        <a href="tel:09449520877">09449520877</a>
      </div>
    </div>
    <div class="email">
      <div class="contact-logo">
        <FaMapMarkerAlt />
      </div>
      <div class="contact-text">
        <a href="mailto:abc@gmail.com">abc@gmail.com</a>
      </div>
    </div>
  </section>

  <section class="link-section">
    <ul class="links">
      <li>
        <a href=".">HOME</a>
      </li>
      <li>
        <a href="about">ABOUT</a>
      </li>
      <li>
        <a href="gallery">GALLERY</a>
      </li>
      <li>
        <a href="mission">MISSION</a>
      </li>
      <li>
        <a href="contact">CONTACT</a>
      </li>
    </ul>
  </section>

</footer>

<div class="footer-copyright">
  © 2019 Ideal English High School. All rights reserved.
</div>
