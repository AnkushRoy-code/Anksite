<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap';
	import Links from './Links.svelte';

	let open = false;
	let sidebar;
	let sidebarWrapper;

	function toggleMenu() {
		open = !open;
		animatePaths(open);
		setOpenState(open);
	}

	function setOpenState(isOpen) {
		open = isOpen;
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
	}

	function handleClickOutside(event) {
		if (open && !sidebar.contains(event.target) && !event.target.closest('.menu-toggle')) {
			setOpenState(false);
			animatePaths(false);
		}
	}

	function animatePaths(isOpen) {
		const topPath = document.getElementById('topPath');
		const middlePath = document.getElementById('middlePath');
		const bottomPath = document.getElementById('bottomPath');

		if (isOpen) {
			gsap.to(topPath, { y: 0, rotation: 45, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 0, duration: 0.1 });
			gsap.to(bottomPath, { y: 0, rotation: -45, duration: 0.3, ease: 'power2.out' });
		} else {
			gsap.to(topPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 1, duration: 0.1, delay: 0.2 });
			gsap.to(bottomPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
		}
	}

	onMount(() => {
		gsap.set(sidebar, { clipPath: 'circle(25px at 2.5em 2.5em)' });
		document.addEventListener('click', handleClickOutside);

		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<div class="sidebar-wrapper" bind:this={sidebarWrapper}>
	<div bind:this={sidebar} class="sidebar">
		<Links />
	</div>
	<button class="menu-toggle" on:click={toggleMenu}>
		<svg width="23" height="23" viewBox="0 0 23 23">
			<path
				id="topPath"
				stroke-width="3"
				stroke="#11111b"
				stroke-linecap="round"
				d="M 2 2.5 L 20 2.5"
			/>
			<path
				id="middlePath"
				stroke-width="3"
				stroke="#11111b"
				stroke-linecap="round"
				d="M 2 9.423 L 20 9.423"
			/>
			<path
				id="bottomPath"
				stroke-width="3"
				stroke="#11111b"
				stroke-linecap="round"
				d="M 2 16.346 L 20 16.346"
			/>
		</svg>
	</button>
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
		background: #89dceb;
	}
	.menu-toggle {
		z-index: 999;
		position: fixed;
		width: 50px;
		height: 50px;
		border-radius: 50%;
		top: 18px;
		left: 9px;
		padding-left: 15px;
		border: none;
		cursor: pointer;
		background: none;
	}
</style>
