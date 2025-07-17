<script>
	import pizzaImage from './Pizza.jpeg';
</script>

<svelte:head>
	<title>Easy Pizza Dough</title>
</svelte:head>
<section class="container">

  <h1 class="name">Easy Pizza Dough</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={pizzaImage} alt="pizza dough">
    </div>
    <div class="ingredients-section">
      <div class="ingredients">
        <h2>Ingredients</h2>
        <ul>
          <li>1 cup of warm water</li>
          <li>1/2 tablespoon of active dry yeast</li>
          <li>1 teaspoon of salt</li>
          <li>4 tablespoons of olive oil</li>
          <li>2 cups of bread flour (king arthur brand)</li>
        </ul>
      </div>
    </div>
    <div class="instructions two_column">
      <h2>Instructions</h2>
      <p>
        Mix it all together in the stand mixer until the dough is smooth and comes off the walls of the bowl cleanly. Cover the bowl with cling wrap and put it in the proofer for 4 hours, or until the dough has doubled in size. You can move the dough to the fridge overnight if you want to make it ahead of time.
      </p>
    </div>
  </div>
</section>

<style>
  /* Recipe-specific styles */
  .two_column {
    grid-column: 1 / -1;
  }

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

  .ingredients-section {
    grid-column: 2 / 3;
    grid-row: 1 / 2;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    height: 100%;
  }

  .ingredients {
    flex: 1;
  }

  .instructions.two_column {
    grid-column: 1 / -1;
    grid-row: 2 / 3;
    margin-top: 1.5rem;
  }

  @media (max-width: 768px) {
    .flex_wrapper {
      grid-template-columns: 1fr;
      grid-template-rows: auto auto auto;
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

    .ingredients-section {
      grid-column: 1 / 2;
      grid-row: 2 / 3;
      height: auto;
    }

    .instructions.two_column {
      grid-column: 1 / 2;
      grid-row: 3 / 4;
      margin-top: 1rem;
    }
  }
</style>
