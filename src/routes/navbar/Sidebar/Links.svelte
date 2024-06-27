<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap';

	const items = ['Something 1', 'Something 2', 'Something 3', 'Something 4', 'Something 5'];

	let links;

	onMount(() => {
		gsap.from(links.children, {
			y: 50,
			opacity: 0,
			stagger: 0.1,
			duration: 0.5,
			ease: 'power2.out'
		});
	});
</script>

<div class="links" bind:this={links}>
	{#each items as item}
		<a href="#{item}" class="link">{item}</a>
	{/each}
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
		gap: 20px;
	}
	.link {
		font-size: 25px;
		color: #c2410c;
		transition: transform 0.2s;
	}
	.link:hover {
		transform: scale(1.1);
	}
	.link:active {
		transform: scale(0.95);
	}
</style>
