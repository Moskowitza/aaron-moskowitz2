<slot />

<style>
	@font-face {
		font-family: 'Libre Caslon Display';
		src: url('./fonts/Libre+Caslon+Display.ttf') format('ttf');
	}
	@font-face {
		font-family: 'Libre Caslon Text';
		src: url('./fonts/Libre+Caslon+Text.ttf') format('ttf');
	}
	
	:global(.name) {
		font-family: 'Libre Caslon Display', 'Times New Roman', Times, regular;
		font-size: clamp(2rem, -0.875rem + 8.333vw, 3.5rem);
	}
	
	:global(.subheading) {
		font-family: 'Libre Caslon Display', 'Times New Roman', Times, regular;
		font-size: clamp(1.5rem, -0.875rem + 8.333vw, 2rem);
		margin-top: 1rem;
	}

	:global(.container) {
		width: min(100% - 1rem, 600px);
		margin-inline: auto;
		margin-block-start: 2rem;
		height: max(3rem, 2rem);
	}
	
	:global(.flex_wrapper) {
		display: grid;
		grid-template-columns: 1fr 2fr;
		align-items: start;
		gap: 0.5rem;
	}

	:global(img) {
		width: min(100% - 1rem, 250px);
		display: inline;
		border-radius: 8px;
		box-shadow: 0 2px 4px rgba(0,0,0,0.1);
	}
	
	:global(.body) {
		font-family: 'Libre Caslon Text', serif;
		font-size: clamp(1rem, 1.25vw, 2rem);
		line-height: 1.5;
		margin-top: 0.5rem;
	}

	:global(ul) {
		list-style-type: disc;
		margin-left: 1.5rem;
	}

	:global(.large-letter::first-letter) {
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
		:global(.container) {
			margin-block-start: 0.5rem;
		}
		:global(.flex_wrapper) {
			grid-template-columns: 1fr;
		}
	}
</style> 
