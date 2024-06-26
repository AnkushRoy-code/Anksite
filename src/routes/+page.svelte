<main>
	<div class="content">
		<div class="list">
			<div class="item"><img src="https://picsum.photos/200/300?random=1" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=2" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=3" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=4" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=5" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=6" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=7" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=8" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=9" alt="image" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=10" alt="image" /></div>
		</div>
	</div>
</main>

<style>
	main {
		background: rgb(2, 2, 82);
		background: linear-gradient(
			139deg,
			rgba(2, 2, 82, 1) 0%,
			rgba(9, 9, 121, 1) 35%,
			rgba(0, 212, 255, 1) 100%
		);
		height: 200vh;
		width: 100vw;
	}

	.content {
		height: 100vh;
		width: 100vw;
	}
	.list {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 10px;

		position: relative;
		top: 50%;
		transform: translateY(-50%);
	}

	.item {
		flex: 0 0 auto;
	}

	.item img {
		width: 9vw; /* Adjust the value to fit all images within the viewport width */
		height: auto; /* Maintains aspect ratio */
		display: block;
	}
</style>
