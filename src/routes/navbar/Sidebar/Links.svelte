<script>
	export let links;
</script>

<div class="links" bind:this={links}>
	<a href="/" class="link">About</a>
	<a href="/" class="link">About</a>
	<a href="/" class="link">About</a>
	<a href="/" class="link">About</a>
	<a href="/" class="link">About</a>
</div>

<style>
	.links {
		position: absolute;
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 40px;
	}
	.link {
		font-size: 25px;
		color: #0b0029;
		transition: transform 0.2s;
	}
	.link:hover {
		transform: scale(1.1);
	}
	.link:active {
		transform: scale(0.95);
	}
</style>
