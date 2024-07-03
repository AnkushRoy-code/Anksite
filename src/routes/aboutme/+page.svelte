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

		gsap.fromTo(
			'.informativeText',
			{ x: '-50vw', y: '50vh' }, // Start position: outside the left side of the viewport
			{
				x: '100vw',
				duration: 5,
				ease: 'power2.inOut', // End position: outside the right side of the viewport
				scrollTrigger: {
					trigger: '.informativeText',
					start: 'top 50%', // When the top of the element is 75% down the viewport
					end: '+=1000', // When the top of the element is 25% down the viewport
					scrub: 2 // Smooth scrubbing
				}
			}
		);

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
				one day.<br /> In this page I have written more about me.
			</p>
		</div>
		<img src="/ankush2.webp" alt="my face" />
	</section>
	<div id="container">
		<div class="informativeText">
			<h1>Heres somethings about me :)</h1>
		</div>

		<section class="left abnormal">
			<h1>Education</h1>
			<p>
				I am currently studying in Agartala, Tripura, India, at Umakanta Academy (English Medium). I
				am in the 11th grade, which is equivalent to high school. I have a keen interest in
				mathematics and science, and I am actively involved in various school clubs and activities.
				I am also preparing for competitive exams like JEE and Olympiads to pursue higher education
				in a top-tier institute.
			</p>
			<h1>Languages</h1>
			<p>
				I am a self-taught programmer, having learned several programming languages such as C++,
				HTML, CSS, JavaScript, and Python. Although I started with Python and only knew the basics,
				I've since expanded my knowledge but have forgotten some of it over time. I also know a
				little bit of Spanish. Aprendí un poco de español con Duolingo pero ahora no tengo tiempo.
				My love for mathematics is immense, and recently, I have developed an interest in graphics
				programming.
			</p>
			<p>
				Additionally, I am fluent in Bengali, Hindi, English, and also know some basic greetings in
				Kokborok (a tribal language), which allows me to communicate effectively with a diverse
				group of people. Learning languages has not only been a way to enhance my programming skills
				but also to explore different cultures and perspectives.
			</p>
		</section>

		<!-- my dev workflow -->
		<section class="right abnormal devworkflow">
			<h1>Dev Workflow</h1>
			<h3>Softwares</h3>
			<p>
				In my dev workflow, I use i3wm with Arch Linux as my daily driver, complemented by Picom for
				compositing and autotiling to manage window layouts efficiently. My primary editor is
				Neovim, which I have customized extensively to suit my coding style. For my terminal
				emulator, I rely on Konsole, and I use Tmux as my terminal multiplexer to handle multiple
				terminal sessions within a single window.
			</p>
			<h3>Keyboard</h3>
			<p>
				I type using the Colemak layout, which I find more comfortable and efficient than the
				traditional QWERTY layout. I also use KMonad for managing keyboard layers, allowing me to
				maximize my productivity by customizing keybindings.
			</p>
			<h3>Laptop Sepcs</h3>
			<p>
				My development machine is an older HP laptop with a Core 2 Duo processor, 3GB of RAM, and a
				300GB HDD. Despite its age, it serves my needs well with a lightweight setup. I use a
				full-sized membrane keyboard and a decent mouse to enhance my workflow.
			</p>
			<p>
				This combination of tools and configurations allows me to maintain a productive and
				efficient development environment, tailored to my preferences and requirements.
			</p>
			<p class="coolbuttoncontainer">
				<a class="coolbutton btn btn--hero" href="https://github.com/AnkushRoy-code/dotfiles"
					>Dev Workflow GitHub</a
				>
			</p>
		</section>

		<section class="down abnormal">
			<h1>that is all there is to me folks!</h1>
		</section>
	</div>
	<section class="normal secondlast">
		<h1>Personal Interests</h1>
		<p>
			I know I said that I said everything about me already but theres more. Beyond my passion for
			programming and mathematics, I have a variety of other interests. I enjoy playing chess and
			often participate in local tournaments to sharpen my strategic thinking skills. In my free
			time, I like to read books on a wide range of topics, from science fiction to historical
			biographies. I also have a growing interest in digital art and have been experimenting with
			creating simple animations using my programming skills. Additionally, I love exploring new
			technologies and keeping up with the latest trends in the tech world.
		</p>
		<p>
			I know that's a lot about me already, but there's more! I have a keen interest in music and
			often find myself exploring different genres to relax and unwind. I also enjoy outdoor
			activities like hiking and cycling, which help me stay active and connected with nature.
			Lastly, I have a passion for cooking and love experimenting with new recipes and cuisines in
			my free time.
		</p>
	</section>
	<section class="normal last"></section>
</main>

<style>
	main {
		background-color: #181825;
		opacity: 1;
		background-size: 80px 80px;
		background-image: repeating-linear-gradient(
			to right,
			#74c7ec,
			#74c7ec 4px,
			#181825 4px,
			#181825
		);
		width: 100 vw;
		overflow-x: hidden;
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
		background-color: #181825;
		opacity: 1;
		background-size: 80px 80px;
		background-image: repeating-linear-gradient(
			to right,
			#74c7ec,
			#74c7ec 4px,
			#181825 4px,
			#181825
		);
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
		background-color: #94e2d5;
	}
	.left {
		background-color: #89b4fa;
	}

	.informativeText {
		position: absolute;
		background-color: #11111b;
		padding: 3rem;
		border-radius: 20px;
		z-index: 1;
	}

	.informativeText h1 {
		color: #cdd6f4;
	}
	.down {
		background-color: #1e1e2e;
	}

	.secondlast {
		background-color: #11111b;
		color: #cdd6f4;
	}

	.last {
		background-color: #f38ba8;
	}

	.left,
	.right,
	.secondlast {
		padding: 4rem;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
	}

	.coolbuttoncontainer {
		display: flex;
	}

	.coolbutton {
		font-size: 1.4rem;
		text-decoration: none;
	}
	.btn {
		display: inline-block;
		position: relative;
		padding: 0.6rem 10px;
		font-weight: bold;
		line-height: 1;
		z-index: 1;
		transition: all cubic-bezier(0.19, 1, 0.22, 1) 0.6s;
		color: #11111b;
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
		border-color: #1e1e2e;
	}

	.btn--hero::after {
		background-color: #1e1e2e;
	}

	.btn--hero:hover {
		-webkit-text-fill-color: #89dceb;
		text-decoration: none;
	}

	.btn--hero:hover::after {
		width: 100%;
	}

	.down {
		display: flex;
		padding: 4rem;
		justify-content: center;
	}
	.down h1 {
		text-transform: capitalize;
		color: #cdd6f4;
	}
</style>
