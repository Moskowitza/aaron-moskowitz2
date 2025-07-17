<script>
  import tokiImage from './Toki.jpeg';
</script>

<svelte:head>
  <title>Toki</title>
  <meta name="description" content="About Moog the cat" />
</svelte:head>

<section class="container">

  <h1 class="name">Toki</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={tokiImage} alt="Toki on the landing">
    </div>
    <div class="content-section">
      <div class="content">
        <h2>About Toki</h2>
        <p>
          Toki was Eno's shy sister. Toki would often find the most impossible hiding spots like under the dishwasher or under the lowest furniture in the house. Eventually Toki settled into my rowhome and became comfortable around everyone, if not a bit suspicious of Blue. Toki often had a skin problem, but not always. We tried so many things over the years to treat her feline alopecia which would flare up now and again.
        </p>
        <p>
          Toki had a few favorite toys over the years, she'd often leave a deteriorating reindeer by the door. She was a pretty smart cat and learned to open our round door knobs. She was also unbelievably strong for a cat nicknamed "Tiny" and a scrappy fighter if you'd try to get her in a crate. 
        </p>
        <p>
          Toki was such a sweetheart and loved to be close with Emily and me. If everything was calm she'd prefer to be on my lap than in a hiding spot. Whenever I hear a dangling wire tap a wall I'll look for Toki's smirk and hear her voice say 'it me.'
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
