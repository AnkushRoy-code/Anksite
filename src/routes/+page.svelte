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
	<div class="area">
		<ul class="circles">
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
		</ul>
	</div>
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
		<h1>My Projects</h1>
		<div class="list">
			<div class="item">
				<a href="/projects#game"><img src="/gameoflife/first.webp" alt="random" /></a>
			</div>
			<div class="item">
				<a href="/projects#game"> <img src="/gameoflife/second.webp" alt="random" /></a>
			</div>
			<div class="item">
				<a href="projects#particle">
					<img src="particle/first.webp" alt="particle simulation" />
				</a>
			</div>
			<div class="item">
				<a href="projects#particle">
					<img src="particle/second.webp" alt="particle simulation two" />
				</a>
			</div>
			<div class="item">
				<a href="projects#eco">
					<img src="ecosight/first.webp" alt="ecosight" />
				</a>
			</div>
			<div class="item">
				<a href="projects#stream">
					<img src="stream/first.webp" alt="streamhub" />
				</a>
			</div>
			<div class="item">
				<a href="projects#stream">
					<img src="stream/second.webp" alt="streamhub two" />
				</a>
			</div>
		</div>
	</div>
</main>

<style>
	main {
		background: rgb(78, 82, 171);
		background: linear-gradient(
			180deg,
			rgba(78, 82, 171, 1) 20%,
			rgb(19, 128, 178) 50%,
			rgba(148, 226, 213, 1) 100%
		);
		height: 200vh;
		height: 200svh;
		width: 100vw;
	}

	.area {
		background: transparent;
		width: 100%;
		height: 200vh;
		position: absolute;
	}

	.circles {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		overflow: hidden;
	}

	.circles li {
		position: absolute;
		display: block;
		list-style: none;
		width: 20px;
		height: 20px;
		background: rgba(147, 153, 178, 0.4);
		animation: animate 25s linear infinite;
		bottom: -150px;
	}

	.circles li:nth-child(1) {
		left: 25%;
		width: 80px;
		height: 80px;
		animation-delay: 0s;
	}

	.circles li:nth-child(2) {
		left: 10%;
		width: 20px;
		height: 20px;
		animation-delay: 2s;
		animation-duration: 12s;
	}

	.circles li:nth-child(3) {
		left: 70%;
		width: 20px;
		height: 20px;
		animation-delay: 4s;
	}

	.circles li:nth-child(4) {
		left: 40%;
		width: 60px;
		height: 60px;
		animation-delay: 0s;
		animation-duration: 18s;
	}

	.circles li:nth-child(5) {
		left: 65%;
		width: 20px;
		height: 20px;
		animation-delay: 0s;
	}

	.circles li:nth-child(6) {
		left: 75%;
		width: 110px;
		height: 110px;
		animation-delay: 3s;
	}

	.circles li:nth-child(7) {
		left: 35%;
		width: 150px;
		height: 150px;
		animation-delay: 7s;
	}

	.circles li:nth-child(8) {
		left: 50%;
		width: 25px;
		height: 25px;
		animation-delay: 15s;
		animation-duration: 45s;
	}

	.circles li:nth-child(9) {
		left: 20%;
		width: 15px;
		height: 15px;
		animation-delay: 2s;
		animation-duration: 35s;
	}

	.circles li:nth-child(10) {
		left: 85%;
		width: 150px;
		height: 150px;
		animation-delay: 0s;
		animation-duration: 11s;
	}

	@keyframes animate {
		0% {
			transform: translateY(0) rotate(0deg);
			opacity: 1;
			border-radius: 0;
			background: rgba(30, 30, 46, 0.4);
		}
		100% {
			transform: translateY(-200vh) rotate(720deg);
			opacity: 0;
			border-radius: 50%;
			background: rgba(210, 217, 245, 0.8);
		}
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

	.content h1 {
		color: var(--mocha-base);
		padding-top: 4rem;
		position: absolute;
		left: 50%;
		transform: translateX(-50%);
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
		height: 50vh;
		display: block;
		object-fit: fill;
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
		filter: brightness(0.1);
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
