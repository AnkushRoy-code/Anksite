<script>
	import Navbar from './navbar/navbar.svelte';
	import Footer from './footer/footer.svelte';

	let isPageLoaded = false;

	const pageLoaded = () => {
		isPageLoaded = true;
	};
</script>

{#if !isPageLoaded}
	<div class="loader" use:pageLoaded>
		<img src="/loader.svg" alt="loading" />
	</div>
{/if}
<Navbar />

<slot />

<Footer />

<style>
	@import '../lib/color.css';

	.loader {
		position: fixed;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		display: grid;
		place-items: center;
		background-color: var(--mocha-crust);
		z-index: 9999;
	}
</style>
