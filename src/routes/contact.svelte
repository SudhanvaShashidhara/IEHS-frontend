<script>
  import { onMount } from "svelte";
  let name = "",
    email = "",
    message = "";

  onMount(() => {});
  function handleContactFormSubmit(event) {
    event.preventDefault();
    console.log("Form Submitted");
    console.log("Name", name);
    console.log("Email", email);
    console.log("Message", message);
  }
</script>

<style>
  #contact-section {
    padding: 2rem 0.5rem;
    width: 100%;
  }

  .contact-form,
  .contact-info {
    border-top: 2px solid var(--main-color-variant);
    width: 95%;
    margin: 2rem auto;
    display: flex;
    flex-direction: column;
  }

  .contact-form > div {
    display: flex;
    flex-direction: row;
    height: 1.8rem;
    width: 90%;
    margin: 2rem auto 0;
  }

  .contact-info > div {
    flex-direction: column;
    padding-top: 1rem;
    text-align: center;
  }

  .contact-info a {
    transition: all 0.3s ease-in;
  }

  .contact-info a:hover,
  .contact-info a:active,
  .contact-info a:focus {
    color: var(--main-secondary-color);
    outline: none;
  }

  .input-container {
    width: 100%;
    position: relative;
  }

  .input-container label {
    position: absolute;
    z-index: 2;
    transition: all 0.3s ease-in;
  }

  label.shrink {
    color: var(--main-color);
    top: -1.4rem;
    left: -0.3rem;
    font-size: 1rem;
  }

  .input-container input,
  .input-container textarea {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100%;
    font-size: 1.4rem;
  }

  input,
  textarea {
    outline: none;
    border: none;
    padding: 0;
    border-bottom: 1px solid red;
  }

  .title {
    color: var(--main-color-variant);
    font-size: 22px;
    margin-bottom: 0.4rem;
  }

  button {
    outline: none;
    background-color: #fff;
    height: 2.5rem;
    padding: 0.3rem 2rem;
    margin: auto;
    text-transform: uppercase;
    font-size: 1.3rem;
    border: 2px solid var(--main-color-variant);
    color: var(--main-color-variant);
    border-radius: 0.2rem;
    transition: all 0.3s ease-in;
  }

  svg {
    width: 12%;
  }

  svg.active {
    color: var(--main-color-variant);
  }

  button:hover,
  button:active,
  button:focus {
    border-color: var(--main-secondary-color);
    color: var(--main-secondary-color);
    background-color: var(--main-color-variant);
  }

  @media only screen and (min-width: 1024px) {
    #contact-section {
      display: flex;
      border-bottom: 2px solid var(--main-color-variant);
    }

    .contact-form {
      border-right: 2px solid var(--main-color-variant);
    }

    .contact-form,
    .contact-info {
      border-top: none;
    }
  }
</style>

<svelte:head>
  <title>Contact Page</title>
</svelte:head>

<section id="contact-section">
  <form on:submit={handleContactFormSubmit} class="contact-form">
    <div class="form-control">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        class={`svelte-c8tyih ${name ? 'active' : ''}`}>
        <path
          d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0
          2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z" />
      </svg>

      <div class="input-container">
        <label class={name ? 'shrink' : ''} for="name">Name</label>
        <input required bind:value={name} type="text" id="name" />
      </div>
    </div>

    <div class="form-control">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        class={`svelte-c8tyih ${email ? 'active' : ''}`}>
        <path
          d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9
          2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z" />
      </svg>
      <div class="input-container">
        <label class={email ? 'shrink' : ''} for="email">E Mail</label>
        <input required bind:value={email} type="email" id="email" />
      </div>
    </div>

    <div class="form-control">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        class={`svelte-c8tyih ${message ? 'active' : ''}`}>
        <path
          d="M3 17.25V21h3.75L17.81 9.94l-3.75-3.75L3 17.25zM20.71
          7.04c.39-.39.39-1.02 0-1.41l-2.34-2.34c-.39-.39-1.02-.39-1.41 0l-1.83
          1.83 3.75 3.75 1.83-1.83z" />
      </svg>
      <div class="input-container">

        <label class={message ? 'shrink' : ''} for="message">Message</label>
        <textarea bind:value={message} id="message" />
      </div>
    </div>

    <div class="form-control">
      <button type="submit" aria-label="Submit Form">Submit</button>
    </div>
  </form>
  <div class="contact-info">
    <div class="address">
      <h5 class="title">Address :</h5>
      <p class="content">
        <a
          target="_blank"
          rel="noopener noreferrer"
          href="https://www.google.co.in/maps/place/Ideal+English+High+School/@13.053981,77.514557,15z/data=!4m5!3m4!1s0x0:0x7d5cda0e0881fed1!8m2!3d13.053981!4d77.514557">
          #70-71, 3rd Main, Bhel Mini Colony, T. Dasarahalli, Bengaluru,
          Karnataka 560057
        </a>
      </p>
    </div>

    <div class="phone">
      <h5 class="title">Phone :</h5>
      <p class="content">
        <a target="_blank" href="tel:09449520877">094495 20877</a>
      </p>
    </div>

    <div class="email">
      <h5 class="title">Email :</h5>
      <p class="content">
        <a target="_blank" href="mailto:abc@gmail.com">abc@gmail.com</a>
      </p>
    </div>
  </div>
</section>
