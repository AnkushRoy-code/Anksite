<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import Links from './Links.svelte';
	import MenuToggle from './MenuToggle.svelte';

	let open = false;
	let sidebar;

	function toggleMenu() {
		open = !open;
		const radius = Math.ceil(window.innerHeight * 1.1);
		if (open) {
			gsap.to(sidebar, {
				clipPath: `circle(${radius}px at 50px 50px)`,
				duration: 0.5,
				ease: 'power4.out'
			});
		} else {
			gsap.to(sidebar, {
				clipPath: 'circle(25px at 2.5em 2.5em)',
				duration: 0.5,
				ease: 'power4.in'
			});
		}
		console.log(open);
	}

	function handleClickOutside(event) {
		if (!sidebar.contains(event.target)) {
			toggleMenu();
		}
	}

	onMount(() => {
		gsap.set(sidebar, { clipPath: 'circle(25px at  2.5em  2.5em)' });
	});
</script>

<div class="sidebar-wrapper">
	<div bind:this={sidebar} class="sidebar">
		<Links />
	</div>
	<MenuToggle on:toggle={toggleMenu} />
</div>

<style>
	.sidebar-wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.sidebar {
		z-index: 999;
		position: fixed;
		top: 0;
		left: 0;
		bottom: 0;
		width: 400px;
		background: #74c7ec;
	}
</style>
