<script>
	export let links;
</script>

<div class="links" bind:this={links}>
	<a href="/" class="link">Home</a>
	<a href="/aboutme" class="link">About Me</a>
	<a href="/projects" class="link">Projects</a>
	<a href="/skills" class="link">Skills</a>
	<a href="/contact" class="link">Contact</a>
	<a href="/achivements" class="link">Achivements</a>
	<a href="/hobbies" class="link">Hobbies And Interests</a>
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
		gap: 5%;
	}
	.link {
		font-size: 25px;
		color: #11111b;
		transition: transform 0.2s;
	}
	.link:hover {
		transform: scale(1.1);
	}
	.link:active {
		transform: scale(0.95);
	}
</style>
