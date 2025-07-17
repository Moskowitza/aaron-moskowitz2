<script>
  import enoImage from './Eno.jpeg';
</script>

<svelte:head>
  <title>Eno</title>
</svelte:head>

<section class="container">

  <h1 class="name">Eno</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={enoImage} alt="Eno the tuxedo cat stickin out her tongue">
    </div>
    <div class="content-section">
      <div class="content">
        <h2>About Eno</h2>
        <p>
          Eno was Toki's sister and protector. I remember the first time meeting Eno and Toki at
          Emily's apartment. Eno came out from under the couch to check me out and determined I was
          worthy of petting her. She was usually happy to meet whoever came over to the house.
        </p>
        <p>
          Eno would love to flop around on the floor knowing I'd get up to rub her soft belly. She
          loved catnip and playing. She was an apt huntress too, quick to take down black flies that
          would sneak in from the back yard. She had her agile years, capable of getting up to trouble
          high on cabinets, toppling a pizza, spilling a pint of curry or picking through the stir-fry.
        </p>
        <p>
          Later in life Eno would keep me company while I worked from home, chirping at the birds
          nesting in the branch just outside the window. Eno learned to ask for food or treats with
          just the right meow. She'd sing too, especially on trips to the vet. She'd sing "AAAAron
          oooooh nooo." My favorite feeling in the world was holding her in my arms.
        </p>
        <p>
          Eno was a great cat and companion. 
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
