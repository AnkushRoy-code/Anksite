<script>
	import Profile from './Profile/Profile.svelte';
</script>

<div class="navbar">
	<h3 class="name">
		Ank<span class="highlight">site</span>
	</h3>
	<div class="right-section">
		<Profile />
	</div>
</div>

<style>
	.navbar {
		background-color: #040b3f;
		margin-top: 1.25rem;
		height: 3.75rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0.75rem 2.5rem;
		position: fixed;
		width: 90vw;
		left: 50%;
		transform: translateX(-50%);
		z-index: 100;
	}

	.name {
		margin-left: 4rem;
		color: #f97316;
		font-size: 1.5rem;
	}

	.highlight {
		color: white;
		border-bottom: 2px solid white;
	}

	.right-section {
		display: flex;
		gap: 0.5rem;
		color: white;
	}
</style>
