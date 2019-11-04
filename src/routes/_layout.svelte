<script>
  import Nav from "../components/Nav.svelte";
  import Footer from "../components/Footer.svelte";

  export let segment;
</script>

<style>
  main {
    /* position: relative; */
    background-color: white;
  }
</style>

<Nav {segment} />

<main>
  <slot />
</main>

<Footer {segment} />
