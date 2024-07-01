<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap/dist/gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	if (typeof window !== 'undefined') {
		gsap.registerPlugin(ScrollTrigger);
	}
	onMount(() => {
		const tl = gsap.timeline();
		tl.from('.left', { xPercent: -100 })
			.from('.right', { xPercent: 100 })
			.from('.down', { yPercent: 100 });

		ScrollTrigger.create({
			animation: tl,
			trigger: '#container',
			start: 'top top',
			end: '+=4000',
			scrub: 2,
			pin: true,
			anticipatePin: 1
		});
	});
</script>

<main>
	<section class="normal first">
		<div class="text">
			<h2>About <span>Me</span></h2>
			<p>
				Hi! My name is <span>Ankush Roy</span> , and I'm a high school student from
				<span>India</span>.<br /> I have passion for <span>mathematics</span> and <span>C++</span>
				programming. <br /> My dream is to become a great <span class="goal">mathematician</span>
				one day.
			</p>
		</div>
		<img src="/ankush2.jpg" alt="my face" />
	</section>
	<div id="container">
		<section class="left abnormal">
			<h1>Hi ai am a text :)</h1>
		</section>
		<section class="right abnormal"></section>
		<section class="down abnormal"></section>
	</div>
	<section class="normal secondlast"></section>
	<section class="normal last"></section>
</main>

<style>
	main {
		background-color: #060032;
		opacity: 0.8;
		background-image: radial-gradient(#00f3ff 2px, transparent 2px),
			radial-gradient(#00f3ff 2px, #060032 2px);
		background-size: 80px 80px;
		background-position:
			0 0,
			40px 40px;
		width: 100 vw;
	}

	section {
		position: relative;
		height: 100vh;
		height: 100lvh;
		width: 100vw;
	}

	.normal {
		width: 100vw;
		height: 100lvh;
	}
	.first {
		background-color: #060032;
		opacity: 1;
		background-image: radial-gradient(#00f3ff 2px, transparent 2px),
			radial-gradient(#00f3ff 2px, #060032 2px);
		background-size: 80px 80px;
		background-position:
			0 0,
			40px 40px;
		color: #cdd6f4;
		display: flex;
		padding: 4rem;
		justify-content: space-between;
	}

	.first div {
		max-width: fit-content;
		max-height: fit-content;
		padding: 2em;
		border-radius: 10px;
		background-color: #11111b80;
		backdrop-filter: blur(4px);
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
	}

	.first div h2 {
		font-size: 6rem;
	}
	.first div h2 span {
		color: #f38ba8;
	}
	.first div p span {
		color: #94e2d5;
	}
	.first div p .goal {
		color: red;
	}
	.abnormal {
		position: absolute;
		top: 0%;
	}
	.right {
		background-color: black;
	}
	.left {
		background-color: blue;
	}

	.left h1 {
		position: relative;
		top: 50%;
	}
	.down {
		background-color: white;
	}

	.secondlast {
		background-color: rgb(8, 40, 69);
	}

	.last {
		background-color: red;
	}
</style>
