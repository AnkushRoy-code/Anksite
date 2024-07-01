<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap/dist/gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	if (typeof window !== 'undefined') {
		gsap.registerPlugin(ScrollTrigger);
	}
	let sections = [];

	const createSectionRefs = (element, index) => {
		sections[index] = element;
	};

	const fadeIn = (section) => {
		const innerSection = section.childNodes[0];
		gsap.to(innerSection, { opacity: 1, scale: 1, duration: 1 });
	};

	const fadeOut = (section) => {
		const innerSection = section.childNodes[0];
		gsap.to(innerSection, { opacity: 0, scale: 0.6, duration: 1 });
	};

	onMount(() => {
		sections.forEach((section, i) => {
			ScrollTrigger.create({
				trigger: section,
				start: 'top 70%',
				end: 'bottom 70%',
				// markers: true,
				onEnter: (self) => {
					const section = self.trigger;
					fadeIn(section);
				},
				onEnterBack: (self) => {
					const section = self.trigger;
					fadeIn(section);
				},
				onLeave: (self) => {
					const section = self.trigger;
					fadeOut(section);
				},
				onLeaveBack: (self) => {
					const section = self.trigger;
					fadeOut(section);
				}
			});
		});
	});
</script>

<main>
	<section bind:this={sections[0]} class="section">
		<div class="innersection"></div>
	</section>
	<section bind:this={sections[1]} class="section">
		<div class="innersection"></div>
	</section>
	<section bind:this={sections[2]} class="section">
		<div class="innersection"></div>
	</section>
	<section bind:this={sections[3]} class="section">
		<div class="innersection"></div>
	</section>
</main>

<style>
	.section {
		position: relative;
		z-index: 0;
		height: 100vh;
		width: 100%;
	}
	.innersection {
		position: absolute;
		top: 20px;
		left: 20px;
		width: calc(100% - 40px);
		height: calc(100% - 40px);

		background-color: #f10707;
		opacity: 0;
		transform: scale(0.6);
	}
</style>
