<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap/dist/gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	if (typeof window !== 'undefined') {
		gsap.registerPlugin(ScrollTrigger);
	}

	onMount(() => {
		gsap.to('.hide', {
			opacity: 0,
			scrollTrigger: {
				trigger: '.hide',
				start: 'top 70%',
				end: 'top 70%'
			}
		});
	});
</script>

<main>
	<section class="landing">
		<div class="container">
			<h1 class="herotitle">
				Hi, my name is <span class="name">Ankush Roy</span>,
				<br />
				I really <span class="love">LOVE</span> Mathematics
			</h1>
			<p class="coolbuttoncontainer">
				<a class="coolbutton btn btn--hero" href="/aboutme">Know more</a>
			</p>
		</div>
		<div class="ankush">
			<img src="/ankush.webp" alt="myself ankush" class="ankushimg" />
		</div>
		<div class="scrolldown">
			<p class="hide">Scroll Down</p>
			<i class="hide fa-solid fa-caret-down"></i>
		</div>
	</section>
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
		height: 400svh;
		width: 100vw;
	}

	.landing {
		min-height: 100vh;
		height: 100vh;
		display: flex;
		align-items: center;
		border-bottom: 0px;
		font-weight: 400;
		color: #11111b;
		padding: 0rem 5.6rem;
		margin-bottom: 0;
		top: 0;
		left: 0;
		bottom: 0;
		right: 0;
		z-index: -1;
	}

	.scrolldown {
		position: absolute;
		top: 95%;
		left: 50%;
		transform: translate(-50%, -50%);
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	.scrolldown p {
		font-weight: 600;
	}

	.scrolldown i {
		animation: moveUpDown 2s ease infinite;
		animation: name duration timing-function delay iteration-count direction fill-mode;
	}

	@keyframes moveUpDown {
		0%,
		100% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-5px);
		}
	}

	.herotitle {
		position: relative;
		font-size: 3.6rem;
		font-weight: 700;
		margin-bottom: 3.2rem;
		text-align: left;
		z-index: 2;
	}

	.coolbuttoncontainer {
		display: flex;
	}

	.coolbutton {
		font-size: 2.4rem;
		text-decoration: none;
	}

	.content {
		height: 100vh;
		height: 100svh;
		width: 100vw;
	}

	.btn {
		display: inline-block;
		position: relative;
		padding: 0.8rem 16px;
		font-weight: bold;
		line-height: 1;
		z-index: 1;
		transition: all cubic-bezier(0.19, 1, 0.22, 1) 0.6s;
		color: var(--mocha-crust);
	}

	.btn::after {
		content: '';
		display: block;
		position: absolute;
		width: 0px;
		height: 100%;
		left: 0;
		bottom: 0;
		z-index: -1;
		transition: all cubic-bezier(0.19, 1, 0.22, 1) 0.3s;
	}

	.btn--hero {
		border-width: 2px;
		border-style: solid;
		border-image-slice: 1;
		border-color: var(--mocha-base);
	}

	.btn--hero::after {
		background-color: var(--mocha-base);
	}

	.btn--hero:hover {
		-webkit-text-fill-color: var(--mocha-sky);
		text-decoration: none;
	}

	.btn--hero:hover::after {
		width: 100%;
	}
	.name {
		color: var(--mocha-sky);
	}
	.love {
		color: var(--mocha-lavender);
	}
	@media (max-width: 500px) {
		.herotitle {
			font-size: 2em;
		}
		.landing {
			padding: 0 1em;
		}
	}

	.ankush {
		height: 468px;
		width: 80%;
		position: absolute;
		z-index: 0;
		right: 6em;
		border-style: solid;
		border-width: 0 8px 8px 0;
		border-color: transparent var(--mocha-green) var(--mocha-green) transparent;
	}
	.ankushimg {
		position: inherit;
		right: 0;
		z-index: 0;
	}
	@media (max-width: 800px) {
		.ankush {
			display: none;
		}
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
