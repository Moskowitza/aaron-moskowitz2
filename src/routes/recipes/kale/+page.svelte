<script>
	import kaleImage from './KaleBowl.jpeg';
</script>

<svelte:head>
	<title>Massaged Kale</title>
	<meta name="description" content="Learn how to make massaged kale with garlic, lemon juice, and olive oil. Perfect side dish that can be served with seitan and potatoes." />
</svelte:head>

<section class="container">

  <h1 class="name">Massaged Kale</h1>
  <div class="flex_wrapper">
    <div class="image-container">
      <img src={kaleImage} alt="Kale prepared with seitan, potatoes, and follow your heart blue cheese">
    </div>
    <div class="ingredients-section">
      <div class="ingredients">
        <h2>Ingredients</h2>
        <ul>
          <li>1 large bag pre-cut and washed kale</li>
          <li>2 tablespoons coarse salt</li>
          <li>2 tablespoons chopped garlic</li>
          <li>4 tablespoons lemon juice</li>
          <li>Olive oil (generous amount)</li>
        </ul>
      </div>
    </div>
    <div class="instructions two_column">
      <h2>Instructions</h2>
      <p>
        Begin by sorting through your kale, removing any remaining stems or imperfect pieces. In a spacious 
        bowl, combine all ingredients and dive in with clean hands to massage the kale leaves thoroughly.
      </p>
      <p>
        The key is to really work the leaves, squeezing and compacting them to break down their fibrous 
        structure. Let the mixture rest for an hour if possible, allowing the flavors to meld. Finally, 
        transfer to a large wok and cook over medium heat for 10-15 minutes, until the kale has reduced 
        significantly in volume and reached your desired tenderness.
      </p>
      <p>
        I often use this kale with seitan, potatoes. I start by cooking the potatoes in a wok that's been heated up with olive oil. I like to use a mix of potato types cut into small cubes. Once the potatoes are soft and some cubes are crispy brown I'll salt and pepper what's in the wok and mix in the seitan. Extra olive oil may be needed if the wok is looking dry. The last step is to mix in the kale and cover the wok. Cook for 10 minutes or until the kale is tender. I'll mix in pine nuts if we have them, they're a great addition. Serve with nutritional yeast, vegan parmesan, or blue cheese.
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
