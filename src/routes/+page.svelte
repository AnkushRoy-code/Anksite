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

	.item img {
		width: 10vw;
		height: auto;
		display: block;
	}

	.list {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1vw;

		position: relative;
		top: 50%;

		transform-style: preserve-3d;
		transform: perspective(1000px) translateY(-50%);
	}

	.item {
		flex: 0 0 auto;
		transition: 0.5s;
		filter: brightness(0);
	}

	.item:hover {
		filter: brightness(1);
		transform: translateZ(200px);
	}

	.item:hover + * {
		filter: brightness(0.6);
		transform: translateZ(150px) rotateY(30deg);
	}
	.item:hover + * + * {
		filter: brightness(0.3);
		transform: translateZ(80px) rotateY(20deg);
	}
	.item:has(+ *:hover) {
		filter: brightness(0.6);
		transform: translateZ(150px) rotateY(-30deg);
	}
	.item:has(+ * + *:hover) {
		filter: brightness(0.3);
		transform: translateZ(80px) rotateY(-20deg);
	}
</style>
