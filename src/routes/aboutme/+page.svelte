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
	<section class="normal first"></section>
	<section class="second"></section>
	<div id="container">
		<section class="left abnormal"></section>
		<section class="right abnormal"></section>
		<section class="down abnormal"></section>
	</div>
	<section class="normal secondlast"></section>
	<section class="normal last"></section>
</main>

<style>
	main {
		background: purple;
		width: 100 vw;
	}
	h1 {
		position: relative;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		text-align: center;
	}
	section {
		position: relative;
		height: 100vh;
		height: 100svh;
		width: 100vw;
	}

	.normal {
		width: 100vw;
		height: 100vh;
	}
	.first {
		background-color: green;
	}
	.second {
		background-color: darkseagreen;
		position: absolute;
		top: 100%;
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
	.down {
		background-color: white;
	}

	.secondlast {
		background-color: aliceblue;
	}

	.last {
		background-color: red;
	}
</style>
