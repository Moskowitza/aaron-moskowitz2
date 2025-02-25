<svelte:head>
	<title>Home</title>
</svelte:head>

<main class="container">
	<h1>Welcome to Our Kitchen & Cats</h1>
	
	<div class="content-sections">
		<section class="nav-section">
			<h2>Our Recipes</h2>
			<nav class="nav-links">
				<a href='/recipes/cookies'>Classic Cookies</a>
				<a href='/recipes/kale'>Massaged Kale</a>
				<a href='/recipes/vegan-chicken-pie'>Vegan Chicken Pie</a>
			</nav>
		</section>

		<section class="nav-section">
			<h2>Meet Our Cats</h2>
			<nav class="nav-links">
				<a href="/cats/elton">Elton</a>
				<a href="/cats/moog">Moog</a>
			</nav>
		</section>

		<section class="nav-section">
			<h2>More</h2>
			<nav class="nav-links">
				<a href="/about">About Aaron</a>
			</nav>
		</section>
	</div>
</main>

<style>
	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem;
		font-family: system-ui, -apple-system, sans-serif;
	}

	h1 {
		font-size: 2.5rem;
		color: #2c3e50;
		text-align: center;
		margin-bottom: 3rem;
		font-weight: 700;
	}

	h2 {
		font-size: 1.5rem;
		color: #34495e;
		margin-bottom: 1rem;
		font-weight: 600;
	}

	.content-sections {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 2rem;
		margin-top: 2rem;
	}

	.nav-section {
		background: #f8f9fa;
		padding: 1.5rem;
		border-radius: 12px;
		box-shadow: 0 2px 4px rgba(0,0,0,0.1);
		transition: transform 0.2s ease;
	}

	.nav-section:hover {
		transform: translateY(-5px);
	}

	.nav-links {
		display: flex;
		flex-direction: column;
		gap: 0.8rem;
	}

	.nav-links a {
		color: #3498db;
		text-decoration: none;
		padding: 0.5rem;
		border-radius: 6px;
		transition: all 0.2s ease;
		font-size: 1.1rem;
	}

	.nav-links a:hover {
		background-color: #3498db;
		color: white;
		padding-left: 1rem;
	}

	@media (max-width: 768px) {
		.container {
			padding: 1rem;
		}

		h1 {
			font-size: 2rem;
			margin-bottom: 2rem;
		}

		.content-sections {
			grid-template-columns: 1fr;
			gap: 1.5rem;
		}
	}
</style>
