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
    background-color: var(--main-color);
    height: 56px;
  }
  .sidebar-button {
    display: flex;
    flex-direction: column;
    outline: none;
    border: none;
    background-color: var(--main-color);
  }
  .sidebar-button:hover {
    cursor: pointer;
  }
  .logo {
    font-size: 1.8rem;
    color: #fff;
  }
  .main-color {
    color: var(--main-color);
  }
  .sidebar-button span {
    background-color: #fff;
    height: 0.4rem;
    width: 2.5rem;
    margin: 0.2rem 0;
  }
  .sidebar-button span:active,
  .sidebar-button span:focus {
    border: 1px solid teal;
  }
  .mobile-nav {
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--main-color-variant);
    height: 100%;
    width: 70%;
    top: 0;
    right: 0;
    z-index: 25;
  }

  .desktop-nav {
    display: none;
  }
  .mobile-nav ul {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    height: 80%;
  }
  ul a {
    font-weight: 900;
    color: #fff;
    height: 100%;
    padding: 0.3rem;
    border-bottom: 0 solid rgb(114, 67, 92);
    transition: all 0.3s ease-in-out;
  }
  ul a.active {
    color: #ffcb00;
  }
  ul a:hover,
  ul a:focus {
    border-bottom: 0.1rem solid var(--main-secondary-color);
  }

  @media only screen and (min-width: 1024px) {
    .sidebar-button {
      display: none;
    }
    .desktop-nav {
      display: block;
      height: 100%;
      display: flex;
      background-color: var(--main-color-variant);
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
  <button
    aria-label="Hamburger Menu"
    on:click={toggleOverlay}
    class="sidebar-button">
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
        <a class={!segment ? 'active' : ''} href=".">HOME</a>
      </li>
      <li>
        <a class={segment === 'about' ? 'active' : ''} href="about">ABOUT</a>
      </li>
      <li>
        <a class={segment === 'gallery' ? 'active' : ''} href="gallery">
          GALLERY
        </a>
      </li>
      <li>
        <a class={segment === 'mission' ? 'active' : ''} href="mission">
          MISSION
        </a>
      </li>
      <li>
        <a class={segment === 'contact' ? 'active' : ''} href="contact">
          CONTACT
        </a>
      </li>

    </ul>
  </nav>
  {#if showOverlayAndSideNav}
    <nav class="mobile-nav open--nav" transition:fade={{ duration: 300 }}>
      <ul class="nav__list">
        <li>
          <a class={!segment ? 'active' : ''} href="." on:click={toggleOverlay}>
            HOME
          </a>
        </li>
        <li>
          <a
            class={segment === 'about' ? 'active' : ''}
            href="about"
            on:click={toggleOverlay}>
            ABOUT
          </a>
        </li>
        <li>
          <a
            class={segment === 'gallery' ? 'active' : ''}
            href="gallery"
            on:click={toggleOverlay}>
            GALLERY
          </a>
        </li>
        <li>
          <a
            class={segment === 'mission' ? 'active' : ''}
            href="mission"
            on:click={toggleOverlay}>
            MISSION
          </a>
        </li>
        <li>
          <a
            class={segment === 'contact' ? 'active' : ''}
            href="contact"
            on:click={toggleOverlay}>
            CONTACT
          </a>
        </li>

      </ul>
    </nav>
  {/if}

</header>
<Overlay showOverlay={showOverlayAndSideNav} {toggleOverlay} />
