<script>
  import moogImage from './moog.jpeg';
</script>

<svelte:head>
  <title>Moog</title>
  <meta name="description" content="About Moog the cat" />
</svelte:head>

<section class="container">

  <h1 class="name">Moog</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={moogImage} alt="Moog the tuxedo cat">
    </div>
    <div class="content-section">
      <div class="content">
        <h2>About Moog</h2>
        <p>
          Originally named Critter, Moog is a petite tuxedo cat with an outsized personality. Despite
          her small stature, she's full of energy and charm. She loves to play fetch with her string
          of felt balls and climb on shoulders like a tiny parrot.
        </p>
        <p>
          When she's not perched up high, you can find her warming up by the fireplace or patiently
          waiting for her food. She shares her home with her brother
          <a href="/pets/elton">Elton</a>.
        </p>
      </div>
    </div>
  </div>
</section>

<style>
  /* Pet-specific styles */
  .name {
    margin-bottom: 2rem;
  }

  .flex_wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto 1fr;
    gap: 1.5rem;
    align-items: start;
  }

  .image-container {
    grid-column: 1 / 2;
    grid-row: 1 / 2;
    height: 100%;
    display: flex;
    align-items: stretch;
  }

  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 8px;
  }

  .content-section {
    grid-column: 2 / 3;
    grid-row: 1 / 2;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    height: 100%;
  }

  .content {
    flex: 1;
  }

  .content h2 {
    font-family: 'Libre Caslon Display', serif;
    font-size: 1.8rem;
    margin-bottom: 1rem;
  }

  .content p {
    font-family: 'Libre Caslon Text', serif;
    line-height: 1.6;
    margin-bottom: 1rem;
  }

  @media (max-width: 768px) {
    .flex_wrapper {
      grid-template-columns: 1fr;
      grid-template-rows: auto auto;
      gap: 1rem;
    }

    .image-container {
      grid-column: 1 / 2;
      grid-row: 1 / 2;
      height: auto;
    }

    .image-container img {
      max-height: 300px;
      object-fit: cover;
    }

    .content-section {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      height: auto;
    }
  }
</style>
