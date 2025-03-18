<script>
  import Nav from '$components/Nav.svelte';
  import '../app.css';
</script>

<Nav />

<main class="content">
  <slot />
</main>

<style>
  .content {
    margin-top: 4rem;
    padding: 2rem;
  }
</style>
