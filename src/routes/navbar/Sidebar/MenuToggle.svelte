<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	function toggle() {
		dispatch('toggle');
	}
</script>

<button class="menu-toggle" on:click={toggle}>
	<svg width="23" height="23" viewBox="0 0 23 23">
		<path stroke-width="3" stroke="#086659" stroke-linecap="round" d="M 2 2.5 L 20 2.5" />
		<path stroke-width="3" stroke="#086659" stroke-linecap="round" d="M 2 9.423 L 20 9.423" />
		<path stroke-width="3" stroke="#086659" stroke-linecap="round" d="M 2 16.346 L 20 16.346" />
	</svg>
</button>

<style>
	.menu-toggle {
		z-index: 999;
		position: fixed;
		width: 50px;
		height: 50px;
		border-radius: 50%;
		top: 19px;
		left: 12px;
		padding-left: 15px;
		border: none;
		cursor: pointer;
		background: none;
	}
</style>
