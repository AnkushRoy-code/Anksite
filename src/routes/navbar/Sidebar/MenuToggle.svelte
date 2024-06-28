<script>
	import { createEventDispatcher } from 'svelte';
	import { gsap } from 'gsap';

	let open = false;
	const dispatch = createEventDispatcher();

	function toggle() {
		open = !open;
		dispatch('toggle', open);

		const topPath = document.getElementById('topPath');
		const middlePath = document.getElementById('middlePath');
		const bottomPath = document.getElementById('bottomPath');

		if (open) {
			gsap.to(topPath, { y: 0, rotation: 45, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 0, duration: 0.1 });
			gsap.to(bottomPath, { y: 0, rotation: -45, duration: 0.3, ease: 'power2.out' });
		} else {
			gsap.to(topPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 1, duration: 0.1, delay: 0.2 });
			gsap.to(bottomPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
		}
	}
</script>

<button class="menu-toggle" on:click={toggle}>
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

<style>
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
