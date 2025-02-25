<svelte:head>
	<title>Elton the Cat</title>
</svelte:head>

<section class="container">
	<h1 class="name">Elton the Cat</h1>
	<div class="flex_wrapper">
		<img src="/elton.jpg" alt="Elton the tuxedo cat and squid toy" class="profile-image" />
		<div>
			<p class="body large-letter">
				Elton, born as "Nuisance," found his forever home through Furever Homes Cat Rescue. This dapper
				tuxedo cat, born on April Fools' Day 2024, brings daily joy and mischief to his family alongside
				his beloved sister <a href="/cats/moog">Moog</a>. His formal black and white attire belies his playful nature.
			</p>
			<p class="body">
				When not engaged in his favorite pastime of toe ambushes, Elton can be found pursuing his
				cherished string-on-a-stick with remarkable agility and determination. His hunting prowess is
				legendary, though his preferred prey tends to be a well-loved stuffed squid that has become his
				constant companion.
			</p>
			<p class="body">
				Despite his initial "Nuisance" moniker, Elton has proven himself to be anything but - transforming
				into a charming and entertaining family member. His synchronized play sessions with Moog and his
				strategic toe-attacking campaigns keep his humans constantly amused and on their toes, quite
				literally.
			</p>
		</div>
	</div>
</section>

<style>
	@font-face {
		font-family: 'Libre Caslon Display';
		src: url('./fonts/Libre+Caslon+Display.ttf') format('ttf');
	}
	@font-face {
		font-family: 'Libre Caslon Text';
		src: url('./fonts/Libre+Caslon+Text.ttf') format('ttf');
	}
	.name {
		font-family: 'Libre Caslon Display', 'Times New Roman', Times, regular;
		font-size: clamp(2rem, -0.875rem + 8.333vw, 3.5rem);
	}

	.container {
		width: min(100% - 1rem, 600px);
		margin-inline: auto;
		margin-block-start: 2rem;
	}

	.flex_wrapper {
		display: grid;
		grid-template-columns: 1fr 2fr;
		align-items: start;
		gap: 0.5rem;
	}

	img {
		width: min(100% - 1rem, 250px);
		display: inline;
	}

	.body {
		font-family: 'Libre Caslon Text', serif;
		font-size: clamp(1rem, 1.25vw, 2rem);
		line-height: 1.5;
		margin-top: 0.5rem;
	}

	.large-letter::first-letter {
		text-transform: none;
		font-family: 'Libre Caslon Text', 'Times New Roman', Times, serif;
		font-feature-settings: normal;
		font-style: normal;
		letter-spacing: normal;
		line-break: auto;
		line-height: 1em;
		font-size: 60px;
		font-weight: 400;
		overflow-wrap: normal;
		float: left;
		margin-bottom: -0.3em;
		padding: 0px 0.05em 0px 0px;
	}

	@media (max-width: 600px) {
		.container {
			margin-block-start: 0.5rem;
		}
		.flex_wrapper {
			grid-template-columns: 1fr;
		}
	}
</style> 
