<main>
	<div class="content">
		<div class="list">
			<div class="item"><img src="https://picsum.photos/200/300?random=1" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=2" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=3" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=4" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=5" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=6" alt="random" /></div>
			<div class="item"><img src="https://picsum.photos/200/300?random=7" alt="random" /></div>
		</div>
	</div>
</main>

<style>
	main {
		background: rgb(78, 82, 171);
		background: linear-gradient(
			180deg,
			rgba(78, 82, 171, 1) 0%,
			rgba(116, 199, 236, 1) 50%,
			rgba(148, 226, 213, 1) 100%
		);
		height: 400vh;
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
