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
			<h2>About Me</h2>
			<p>
				Hi! My name is Ankush Roy, and I'm a high school student from India.<br /> I have passion
				for mathematics and C++ programming. <br /> My dream is to become a great mathematician one day.
			</p>
		</div>
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
	}

	.first div {
		max-width: fit-content;
		padding: 2em;
		border-radius: 10px;
		background-color: #11111b;
		position: relative;
		display: grid;
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
