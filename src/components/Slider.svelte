<script>
  export let sliderData,
    delay,
    auto = false;
  let nextSlide, prevSlide;
  import { onMount } from "svelte";
  onMount(() => {
    document.querySelector(".slide").classList.add("current");
    const slides = document.querySelectorAll(".slide");
    const next = document.getElementById("next");
    const prev = document.getElementById("prev");
    const intervalTime = delay;
    let slideInterval;
    nextSlide = () => {
      const current = document.querySelector(".current");
      current.classList.remove("current");
      if (current.nextElementSibling) {
        current.nextElementSibling.classList.add("current");
      } else {
        slides[0].classList.add("current");
      }
      setTimeout(() => current.classList.remove("current"), 0);
      if (auto) {
        clearInterval(slideInterval);
        slideInterval = setInterval(nextSlide, delay);
      }
    };
    prevSlide = () => {
      const current = document.querySelector(".current");
      current.classList.remove("current");
      if (current.previousElementSibling) {
        current.previousElementSibling.classList.add("current");
      } else {
        slides[slides.length - 1].classList.add("current");
      }
      setTimeout(() => current.classList.remove("current"), 0);
      if (auto) {
        clearInterval(slideInterval);
        slideInterval = setInterval(nextSlide, delay);
      }
    };
    if (auto) {
      slideInterval = setInterval(nextSlide, delay);
    }
    return () => clearInterval(slideInterval);
  });
</script>

<style>
  .slider {
    position: relative;
    overflow: hidden;
    height: 100vh;
    width: 100vw;
  }
  .slide {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    transition: opacity 0.4s ease-in-out;
  }
  :global(.current) {
    opacity: 0.6 !important;
  }
  .content {
    position: absolute;
    bottom: 5rem;
    padding: 1rem;
    width: 100%;
    bottom: -21rem;
    left: 0;
    opacity: 0;
    background-color: rgba(255, 255, 255, 0.8);
    color: #333;
    transition: all 0.7s ease-in-out 0.3s;
  }
  :global(.current .content) {
    opacity: 1 !important;
    transform: translateY(-21rem) !important;
    transition: all 0.7s ease-in-out 0.3s !important;
  }
  h1 {
    margin-bottom: 0.6rem;
  }
  button {
    width: 2.7rem;
    height: 2.7rem;
    border: 2px solid #fff;
    background-color: transparent;
    cursor: pointer;
    padding: 0.7rem;
    border-radius: 50%;
    outline: none;
  }
  button:hover {
    background-color: #fff;
  }
  button:hover svg {
    fill: #333;
  }
  svg {
    fill: #fff;
  }
  #prev {
    position: absolute;
    top: 45%;
    left: 1rem;
  }
  #next {
    position: absolute;
    top: 45%;
    right: 1rem;
  }
  @media (min-width: 768px) {
  }
  @media (min-width: 992px) {
  }
  @media (min-width: 1200px) {
    .content {
      width: 70%;
      padding: 2rem;
      bottom: 0rem;
      left: -70%;
    }
    :global(.current .content) {
      opacity: 1 !important;
      transform: translateX(100%) !important;
      transition: all 0.7s ease-in-out 0.3s !important;
    }
    button {
      width: 2.8rem;
      height: 2.8rem;
    }
  }
</style>

<div class="slider">
  {#each sliderData as slide}
    <div
      class="slide"
      style="background: url({slide.imageUrl}) no-repeat center center/cover;">
      <div class="content">
        <h1>{slide.cardTitle}</h1>
        <p>{slide.cardText}</p>
      </div>
    </div>
  {/each}
</div>
<div class="buttons">
  <button id="prev" on:click={prevSlide}>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 448 512"
      class="svelte-c8tyih">
      <path
        d="M257.5 445.1l-22.2 22.2c-9.4 9.4-24.6 9.4-33.9 0L7
        273c-9.4-9.4-9.4-24.6 0-33.9L201.4 44.7c9.4-9.4 24.6-9.4 33.9 0l22.2
        22.2c9.5 9.5 9.3 25-.4 34.3L136.6 216H424c13.3 0 24 10.7 24 24v32c0
        13.3-10.7 24-24 24H136.6l120.5 114.8c9.8 9.3 10 24.8.4 34.3z" />
    </svg>
  </button>
  <button id="next" on:click={nextSlide}>
    <svg
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 448 512"
      class="svelte-c8tyih">
      <path
        d="M190.5 66.9l22.2-22.2c9.4-9.4 24.6-9.4 33.9 0L441 239c9.4 9.4 9.4
        24.6 0 33.9L246.6 467.3c-9.4 9.4-24.6 9.4-33.9
        0l-22.2-22.2c-9.5-9.5-9.3-25 .4-34.3L311.4 296H24c-13.3
        0-24-10.7-24-24v-32c0-13.3 10.7-24 24-24h287.4L190.9
        101.2c-9.8-9.3-10-24.8-.4-34.3z" />
    </svg>
  </button>
</div>
