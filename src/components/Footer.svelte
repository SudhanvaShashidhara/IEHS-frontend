<script>
  export let segment;
  import FaMapMarkerAlt from "svelte-icons/fa/FaMapMarkerAlt.svelte";
  import FaPhone from "svelte-icons/fa/FaPhone.svelte";
  import FaEnvelope from "svelte-icons/fa/FaEnvelope.svelte";
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
    margin: 1rem auto 0;
  }
  .link-section {
    margin-bottom: 1rem;
  }
  h3 {
    text-align: center;
    color: var(--main-secondary-color);
    margin-bottom: 1.2rem;
    border-bottom: 1px solid var(--main-secondary-color);
    padding-bottom: 0.5rem;
  }
  .address,
  .phone,
  .email {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem;
  }
  .contact-logo {
    width: 8%;
    color: var(--main-secondary-color);
  }
  .contact-text {
    width: 85%;
  }
  .links {
    text-align: center;
  }
  .active {
    background-color: var(--main-color-variant);
    border-radius: 0.3rem;
    border: 1px solid rgba(250, 33, 33, 0.9);
    color: var(--main-secondary-color);
  }

  ul li {
    min-height: 48px;
  }

  ul a {
    min-height: 48px;
    transition: all 0.3s ease-in-out;
  }
  ul a:hover,
  ul a:focus {
    border-bottom: 0.1rem solid var(--main-secondary-color);
  }
  .footer-copyright {
    padding: 0.9rem;
    background-color: var(--main-color-variant);
    color: #fff;
  }

  @media only screen and (min-width: 1024px) {
    footer {
      flex-direction: row;
      padding: 2rem 15%;
    }
    section {
      width: 70%;
      margin: 1rem auto;
    }

    .contact-section {
      border-right: 1px solid var(--main-secondary-color);
    }

    section > div {
      padding-bottom: 1rem;
    }

    .links {
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      height: 70%;
    }

    .links li {
      margin: 0 2rem;
    }
  }
</style>

<footer>
  <section class="contact-section">
    <h3>GET IN TOUCH</h3>
    <div class="address">
      <div class="contact-logo">
        <FaMapMarkerAlt />
      </div>
      <div class="contact-text">
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://www.google.co.in/maps/place/Ideal+English+High+School/@13.053981,77.514557,15z/data=!4m5!3m4!1s0x0:0x7d5cda0e0881fed1!8m2!3d13.053981!4d77.514557">
          #70-71, 3rd Main, Bhel Mini Colony, T. Dasarahalli, Bhel Mini Colony,
          Jalahalli West, Bengaluru, Karnataka 560057
        </a>
      </div>
    </div>
    <div class="phone">
      <div class="contact-logo">
        <FaPhone />
      </div>
      <div class="contact-text">
        <a target="_blank" rel="noopener noreferrer" href="tel:09449520877">
          09449520877
        </a>
      </div>
    </div>
    <div class="email">
      <div class="contact-logo">
        <FaEnvelope />
      </div>
      <div class="contact-text">
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="mailto:abc@gmail.com">
          abc@gmail.com
        </a>
      </div>
    </div>
  </section>

  <section class="link-section">
    <h3>LINKS</h3>
    <ul class="links">
      <li class={!segment ? 'active' : ''}>
        <a href=".">Home</a>
      </li>
      <li class={segment === 'about' ? 'active' : ''}>
        <a href="about">About</a>
      </li>
      <li class={segment === 'gallery' ? 'active' : ''}>
        <a href="gallery">Gallery</a>
      </li>
      <li class={segment === 'mission' ? 'active' : ''}>
        <a href="mission">Mission</a>
      </li>
      <li class={segment === 'contact' ? 'active' : ''}>
        <a href="contact">Contact</a>
      </li>
    </ul>
  </section>

</footer>

<div class="footer-copyright">
  © {new Date().getFullYear()} Ideal English High School. All rights reserved.
</div>
