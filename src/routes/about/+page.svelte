
<svelte:head>
	<title>Aaron Moskowitz</title>
</svelte:head>
<section class="container">
	<h1 class="name">Aaron Moskowitz</h1>
	<div class="flex_wrapper">
        <img src="/profile.png" alt="Aaron Moskowitz" class="profile-image" />
		<div>
			<p class="body large-letter">
				Aaron here! I'm currently the Supervisor of Application Development at Rothman Orthopaedics
				where I build and maintain full stack Javascript applications.
			</p>
			<p class="body">
				I began working with healthcare organizations after obtaining my masters in Biomedical
				Engineering. I enjoy rock climbing, vegan food, and baking bread.
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
		height: max(3rem, 2rem);
	}
	.flex_wrapper {
		display: grid;
		grid-template-columns: 1fr 2fr;
		align-items: end;
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
		/* width: min(100% - 1rem, 200px); */
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
