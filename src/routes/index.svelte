<style>
  section.hero-image {
    position: relative;
  }

  .hero-image img {
    min-height: 180px;
  }
  img {
    width: 100%;
  }

  section.hero-image::before {
    content: "";
    position: absolute;
    background-color: var(--main-secondary-variant);
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  .content-box {
    position: absolute;
    text-align: center;
    color: #fff;
    background-color: var(--main-color);
    width: 60%;
    margin: auto;
    bottom: 0;
    left: 20%;
    padding: 0.5rem;
  }

  .o-wrapper {
    display: flex;
    flex-direction: column;
    text-align: center;
  }

  .o-card {
    padding: 1rem;
  }

  .o-image {
    position: relative;
  }

  .o-image::after {
    content: "";
    position: absolute;
    border-right: 3rem solid var(--main-secondary-color);
    border-top: 3rem solid transparent;
    right: 0;
    bottom: 0.35rem;
  }

  .o-info button {
    padding: 0.5rem;
    border: 0.1rem solid var(--main-color-variant);
    background-color: transparent;
    color: var(--main-color-variant);
    transition: all 0.3s ease-in;
  }

  .o-info button:hover,
  .o-info button:active {
    background-color: var(--main-color-variant);
    color: var(--main-secondary-color);
    border-color: var(--main-secondary-color);
  }

  @media (min-width: 480px) {
    section.hero-image img {
      max-height: 80vh;
    }

    .content-box {
      background-color: var(--main-color-variant);
      top: 1.5rem;
      bottom: auto;
      width: 25%;
      left: 37.5%;
    }

    .o-container {
      width: 80%;
      margin: 2rem auto;
    }

    .o-wrapper {
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-between;
    }

    .o-card {
      width: 40%;
    }

    .o-card img {
      height: 14rem;
    }
  }

  @media only screen and (min-width: 1024px) {
    .hero-image img {
      min-height: 580px;
    }
  }
</style>

<svelte:head>
  <title>Ideal English High School – Bengaluru, Karnataka</title>
</svelte:head>

<main>
  <section class="hero-image">
    <img src="./Home-hero.jpg" alt="Home Page" />
    <div class="content-box">
      <h3>Preparing & Nurturing</h3>
      <p>Global Citizens of the future</p>
    </div>
  </section>

  <section class="o-container">
    <div class="o-wrapper">

      <div class="o-card">
        <div class="o-image">
          <img
            src="./home-connection-section-1.jpg"
            alt="home-connection-section-1" />
        </div>
        <div class="o-info">
          <h3>Academics @ IEHS</h3>
          <p>
            Providing each student with the opportunity to achieve, through an
            exciting and progressive curriculum.
          </p>
          <button>Read More</button>

        </div>
      </div>

      <div class="o-card">
        <div class="o-image">
          <img
            src="./home-connection-section-2.jpg"
            alt="home-connection-section-2" />
        </div>
        <div class="o-info">
          <h3>Admission Details</h3>
          <p>Admissions are open for the academic year 2018-19.</p>
          <button>Read More</button>
        </div>
      </div>

      <div class="o-card">
        <div class="o-image">
          <img
            src="./home-connection-section-3.jpg"
            alt="home-connection-section-3" />
        </div>
        <div class="o-info">
          <h3>Events @ IEHS</h3>
          <p>Take a look at latest happenings.</p>
          <button>Read More</button>
        </div>
      </div>

    </div>
  </section>
</main>
