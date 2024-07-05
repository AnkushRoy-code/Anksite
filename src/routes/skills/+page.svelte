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
		gsap.to(innerSection, { opacity: 1, scale: 1, duration: 0.5 });
	};

	const fadeOut = (section) => {
		const innerSection = section.childNodes[0];
		gsap.to(innerSection, { opacity: 0, scale: 0.6, duration: 0.5 });
	};

	onMount(() => {
		sections.forEach((section, i) => {
			ScrollTrigger.create({
				trigger: section,
				start: 'top 50%',
				end: 'bottom 20%',
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
	<div class="skillshead"><h1>my skills</h1></div>
	<section bind:this={sections[0]} class="section">
		<div class="innersection first">
			<h1>Programming Skills</h1>
			<ul>
				<li>
					<strong>C++:</strong> Advanced knowledge, including graphics programming with OpenGL and SDL2,
					and learning ray tracing.
				</li>
				<li>
					<strong>Python:</strong> Basic understanding; started learning with Python but now primarily
					focus on C++.
				</li>
				<li>
					<strong>HTML & CSS:</strong> Proficient in creating web pages with a strong grasp of CSS for
					styling.
				</li>
				<li><strong>JavaScript:</strong> Basic knowledge for enhancing web interactivity.</li>
			</ul>
		</div>
	</section>
	<section bind:this={sections[1]} class="section">
		<div class="innersection second">
			<h1>Mathematics Skills</h1>
			<ul>
				<li><strong>Algebra:</strong> Strong grasp of algebraic concepts and problem-solving.</li>
				<li><strong>Calculus:</strong> Proficient in both differential and integral calculus.</li>
				<li>
					<strong>Geometry:</strong> In-depth understanding of geometric principles and their applications.
				</li>
				<li>
					<strong>Statistics & Probability:</strong> Basic knowledge, with interest in exploring further.
				</li>
			</ul>
		</div>
	</section>
	<section bind:this={sections[2]} class="section">
		<div class="innersection third">
			<h1>Tools & Technologies</h1>
			<ul>
				<li>
					<strong>i3wm:</strong> Window manager used with Arch Linux, along with Picom and autotiling
					for efficient workflow.
				</li>
				<li><strong>Neovim:</strong> Primary text editor with extensive customizations.</li>
				<li>
					<strong>Konsole:</strong> Terminal emulator of choice, paired with Tmux for terminal multiplexing.
				</li>
				<li>
					<strong>KMonad:</strong> Used for managing keyboard layers, and typing with the Colemak layout.
				</li>
				<li>
					<strong>Git:</strong> Proficient in version control using Git, essential for collaborative
					projects and managing code versions.
				</li>
			</ul>
		</div>
	</section>
	<section bind:this={sections[3]} class="section">
		<div class="innersection fourth">
			<h1>Other Skills</h1>
			<ul>
				<li>
					<strong>Languages:</strong> Fluent in Bengali, Hindi, English, Kokborok, and basic Spanish.
				</li>
				<li>
					<strong>Chess:</strong> Experienced player, with participation and wins in local tournaments.
				</li>
				<li>
					<strong>Open Source Contributions:</strong> Active contributor to various open-source projects.
				</li>
				<li>
					<strong>Problem-Solving:</strong> Strong analytical skills honed through mathematics and programming
					challenges.
				</li>
			</ul>
		</div>
	</section>
</main>

<style>
	@import '../../lib/color.css';

	main {
		background-color: var(--mocha-sapphire);
		padding-top: 1rem;
	}

	.skillshead {
		position: relative;
		width: 80%;
		background-color: var(--mocha-crust);
		text-transform: capitalize;
		left: 50%;
		transform: translateX(-50%);
		color: var(--mocha-subtext0);

		padding: 1rem;
		border-radius: 20px;

		display: flex;
		justify-content: center;
	}

	.section {
		position: relative;
		z-index: 0;
		height: 50vh;
		width: 100%;
	}
	.innersection {
		position: absolute;
		top: 20px;
		left: 20px;
		width: calc(100% - 40px);
		height: calc(100% - 40px);

		opacity: 0;
		transform: scale(0.6);

		padding: 4rem;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;

		border-radius: 20px;
	}
	.first {
		background-color: var(--mocha-base);
		color: var(--mocha-text);
	}
	.second {
		background-color: var(--mocha-mantle);
		color: var(--mocha-subtext1);
	}
	.third {
		background-color: var(--mocha-crust);
		color: var(--mocha-subtext0);
	}
	.fourth {
		background-color: var(--mocha-surface0);
		color: var(--mocha-lavender);
	}
</style>
