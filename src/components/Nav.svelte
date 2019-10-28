<script>
  import Overlay from "./Overlay.svelte";
  import { fade } from "svelte/transition";
  export let segment;

  let showOverlayAndSideNav = false;
  function toggleOverlay() {
    showOverlayAndSideNav = !showOverlayAndSideNav;
  }
</script>

<style>
  header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 0.4rem 0.6rem;
    background-color: rgb(148, 43, 43);
    height: 56px;
  }
  .sidebar-button {
    display: flex;
    flex-direction: column;
    outline: none;
    border: none;
    background-color: rgb(148, 43, 43);
  }
  .logo {
    font-size: 1.8rem;
  }
  .main-color {
    color: var(--main-color);
  }
  .sidebar-button span {
    background-color: black;
    height: 0.4rem;
    width: 2.5rem;
    margin: 0.2rem 0;
  }
  .mobile-nav {
    position: fixed;
    background-color: rgba(148, 43, 43, 0.8);
    height: 100%;
    width: 60%;
    top: 0;
    right: 0;
    z-index: 25;
    transform: translateX(100%);
    transition: all 3s ease-in-out;
  }
  .open--nav {
    transform: translateX(0%);
  }
  .desktop-nav {
    display: none;
  }
  .mobile-nav ul {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 100%;
  }

  @media only screen and (min-width: 1024px) {
    .sidebar-button {
      display: none;
    }
    .desktop-nav {
      display: block;
    }
    .nav__list {
      display: flex;
      flex-direction: row;
    }
    .nav__list li {
      margin: auto 0.5rem;
    }
  }
</style>

<header>
  <button on:click={toggleOverlay} class="sidebar-button">
    <span class="bar-one" />
    <span class="bar-two" />
    <span class="bar-three" />
  </button>
  <h4 class="logo">
    {#if showOverlayAndSideNav}
      <a class="main-color" href=".">IEHS</a>
    {:else}
      <a href=".">IEHS</a>
    {/if}
  </h4>
  <nav class="desktop-nav">
    <ul class="nav__list">
      <li>
        <a href=".">Home</a>
      </li>
      <li>
        <a href="about">About</a>
      </li>
      <li>
        <a href="gallery">Gallery</a>
      </li>
      <li>
        <a href="mission">Mission</a>
      </li>
      <li>
        <a href="contact">Contact</a>
      </li>

    </ul>
  </nav>
  {#if showOverlayAndSideNav}
    <nav class="mobile-nav open--nav" transition:fade={{ duration: 300 }}>
      <ul class="nav__list">
        <li>
          <a href="." on:click={toggleOverlay}>Home</a>
        </li>
        <li>
          <a href="about" on:click={toggleOverlay}>About</a>
        </li>
        <li>
          <a href="gallery" on:click={toggleOverlay}>Gallery</a>
        </li>
        <li>
          <a href="mission" on:click={toggleOverlay}>Mission</a>
        </li>
        <li>
          <a href="contact" on:click={toggleOverlay}>Contact</a>
        </li>

      </ul>
    </nav>
  {/if}

</header>
<Overlay showOverlay={showOverlayAndSideNav} {toggleOverlay} />
