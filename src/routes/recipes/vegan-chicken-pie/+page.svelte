<script>
  import squirrelandcorn from './squirrelandcorn.jpeg';
</script>

<svelte:head>
  <title>Vegan Chicken Pie Recipe</title>
</svelte:head>

<section class="container">

  <h1 class="name">Vegan Chicken Pie</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={squirrelandcorn} alt="Squirrel and Corn">
    </div>
    <div class="ingredients-section">
      <div class="ingredients">
        <h2>Filling</h2>
        <ul>
          <li>2 tablespoons olive oil</li>
          <li>1 small onion, chopped</li>
          <li>3 garlic cloves, minced</li>
          <li>⅓ cup all-purpose flour</li>
          <li>2 cups vegetable broth</li>
          <li>1 cup unsweetened almond milk</li>
          <li>3 cups frozen mixed vegetables (carrots, corn, green beans, peas)</li>
          <li>1 large russet potato, chopped into small chunks</li>
          <li>8 ounces vegan "chicken" or baked tofu, cut into chunks (optional)</li>
          <li>½ teaspoon salt, or to taste</li>
          <li>1 prepared pie crust</li>
        </ul>
      </div>
      <div class="ingredients">
        <h2>Pie Crust</h2>
        <ul>
          <li>1 1/2 cups of flour</li>
          <li>1 tsp sugar</li>
          <li>1/4 tsp salt</li>
          <li>1/4 cup earth balance</li>
          <li>1/4 cup crisco</li>
          <li>4 tbsp water (ice cold)</li>
        </ul>
      </div>
    </div>
    <div class="instructions two_column">
      <h2>Instructions</h2>
      <p>
        Preheat your oven to 400°F (200°C). In a large skillet, heat olive oil over medium heat. Add
        the chopped onion and sauté until translucent, then add minced garlic and cook until
        fragrant.
      </p>
      <p>
        Gradually whisk in the flour to create a roux, cooking for about a minute. Slowly pour in
        the vegetable broth and almond milk, whisking constantly to prevent lumps. Add the frozen
        vegetables, potato chunks, and vegan chicken or tofu. Simmer until the sauce thickens and
        the vegetables are tender. Season with salt to taste.
      </p>
      <p>
        Pour the filling into your prepared pie crust, ensuring an even distribution. Place pie pan on a rack above a baking tray to catch drips. Bake in the
        preheated oven for 45 minutes, or until the crust is golden brown and the filling is
        bubbling. Let cool for 10 minutes before serving.
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
