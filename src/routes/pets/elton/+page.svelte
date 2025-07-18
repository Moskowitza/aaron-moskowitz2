<script>
  import eltonImage from './Elton.jpg';
</script>

<svelte:head>
  <title>Elton</title>
  <meta name="description" content="Meet Elton, the playful tuxedo cat born on April Fools' Day 2024. A mischievous rescue cat who loves toe ambushes and string-on-a-stick games." />
</svelte:head>

<section class="container">

  <h1 class="name">Elton John</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={eltonImage} alt="Elton the tuxedo cat and squid toy">
    </div>
    <div class="content-section">
      <div class="content">
        <h2>About Elton</h2>
        <p>
          Elton, born as "Nuisance," found his forever home through Furever Homes Cat Rescue. This
          dapper tuxedo cat, born on April Fools' Day 2024, brings daily joy and mischief to his
          family alongside his beloved sister <a href="/pets/moog">Moog</a>. His formal black and
          white attire belies his playful nature.
        </p>
        <p>
          When not engaged in his favorite pastime of toe ambushes, Elton can be found pursuing his
          cherished string-on-a-stick with remarkable agility and determination. His hunting prowess
          is legendary, though his preferred prey tends to be a well-loved stuffed squid that has
          become his constant companion.
        </p>
        <p>
          Despite his initial "Nuisance" moniker, Elton has proven himself to be anything but -
          transforming into a charming and entertaining family member. His synchronized play sessions
          with Moog and his strategic toe-attacking campaigns keep his humans constantly amused and on
          their toes, quite literally.
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
