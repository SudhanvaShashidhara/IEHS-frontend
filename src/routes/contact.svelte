<script>
  import IoMdPerson from "svelte-icons/io/IoMdPerson.svelte";
</script>

<style>
  #contact-section {
    margin: 2rem 1rem;
  }
</style>

<svelte:head>
  <title>Contact Page</title>
</svelte:head>

<section id="contact-section">
  <form class="contact-form">
    <div class="form-control">
      <label for="name">Name</label>
      <input type="text" id="name" />
    </div>

    <div class="form-control">
      <label for="email">E Mail</label>
      <input type="email" id="email" />
    </div>

    <div class="form-control">
      <label for="message">Message</label>
      <textarea id="message" />
    </div>
  </form>
  <div class="contact-info" />
</section>
