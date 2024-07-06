<main>
	<section id="game" class="gameOfLife">
		<div class="container">
			<div class="text">
				<h1>Conway's Game Of Life</h1>
				<p>
					Conway's Game of Life is a cellular automaton devised by mathematician John Conway. In my
					implementation using C++ and the SDL2 library, I've added several interactive features to
					enhance the user experience. You can pan and zoom around the grid to explore different
					areas, pause and play the simulation to closely observe the changes, and randomly fill the
					grid to start with varied initial conditions. Additionally, there's a feature to clear the
					grid for a fresh start. These enhancements make it easier to observe and understand the
					complex, emergent behaviors that arise from Conway's simple rules.
				</p>
				<div class="buttons">
					<p class="coolbuttoncontainer">
						<a class="coolbutton btn btn--hero" href="https://github.com/AnkushRoy-code/gameOfLife"
							>GitHub Repo</a
						>
					</p>
				</div>
			</div>
			<img src="/gameoflife/gameOfLife.webp" alt="" />
		</div>
	</section>
	<section id="eco" class="EcoSight">
		<div class="container">
			<div class="text">
				<h1>Ecosight</h1>
				<p>
					This project, developed by my team and me during a GeeksForGeeks hackathon. We created an
					innovative application that provides analytical insights through an intuitive online
					interface. Our work focused on environmental concerns, featuring analyses such as carbon
					footprint assessment and satellite image classification.
				</p>
				<div class="buttons">
					<p class="coolbuttoncontainer">
						<a
							class="coolbutton btn btn--hero"
							href="https://github.com/ShibamRoy9826/EcoSight-Geek-a-thon-project">GitHub Repo</a
						>
					</p>
					<p class="coolbuttoncontainer">
						<a class="coolbutton btn btn--hero" href="https://ecosight.pythonanywhere.com/"
							>Website</a
						>
					</p>
				</div>
			</div>
			<img src="/ecosight/ecosight.webp" alt="" />
		</div>
	</section>
	<section id="particle" class="ParticleLife">
		<div class="container">
			<div class="text">
				<h1>Particle Life Simulation</h1>
				<p>
					I created a Particle Life simulation using C++, SDL2, and Dear ImGui. This application
					holds a special place for me due to the unique and amusing patterns it generates. Inspired
					by the concept of cellular automata, originally developed by Stephen Wolfram, this project
					is my implementation of particle-based simulations. It showcases my skills in combining
					physics-based simulations with interactive graphics, resulting in fascinating and
					unpredictable behaviors. You just watch particles react with themselves beautifully with
					just some simple defined rules.
				</p>
				<div class="buttons">
					<p class="coolbuttoncontainer">
						<a class="coolbutton btn btn--hero" href="https://github.com/AnkushRoy-code/Particle"
							>GitHub Repo</a
						>
					</p>
				</div>
			</div>
			<img src="/particle/particle.webp" alt="" />
		</div>
	</section>
	<section id="stream" class="StreamerHub">
		<div class="container">
			<div class="text">
				<h1>Streamer Hub</h1>
				<p>
					I developed StreamerHub, a frontend application using React and GSAP. StreamerHub serves
					as a professional hub for streamers, featuring a sleek and interactive user interface. The
					application focuses on providing a seamless experience for users to manage and showcase
					their streaming content effectively. With React's framework and GSAP's animation
					capabilities, StreamerHub delivers a dynamic and visually engaging platform tailored for
					streamers and their audiences.
				</p>
				<div class="buttons">
					<p class="coolbuttoncontainer">
						<a class="coolbutton btn btn--hero" href="https://github.com/AnkushRoy-code/StreamerHub"
							>GitHub Repo</a
						>
					</p>
				</div>
			</div>
			<img src="/stream/stream.webp" alt="" />
		</div>
	</section>
</main>

<style>
	main {
		background: rgb(78, 82, 171);
		background: linear-gradient(
			135deg,
			rgba(78, 82, 171, 1) 0%,
			rgba(116, 199, 236, 1) 50%,
			rgba(148, 226, 213, 1) 100%
		);

		width: 100svw;
	}

	section .container {
		min-height: 100vh;
		width: 100vw;
		overflow: hidden;
		padding: 4rem;

		display: flex;
	}
	section div img {
		max-width: 60vw;
		max-height: 80vh;
		height: auto;
		object-fit: contain;
	}

	.gameOfLife {
		background-color: var(--mocha-crust);
		color: var(--mocha-subtext0);
	}
	.EcoSight {
		background-color: var(--mocha-base);
		color: var(--mocha-text);
	}
	.ParticleLife {
		background-color: var(--mocha-mantle);
		color: var(--mocha-subtext1);
	}
	.StreamerHub {
		background-color: var(--mocha-crust);
		color: var(--mocha-subtext0);
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
		color: var(--mocha-lavender);
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
		border-color: var(--mocha-lavender);
	}

	.btn--hero::after {
		background-color: var(--mocha-lavender);
	}

	.btn--hero:hover {
		-webkit-text-fill-color: var(--mocha-crust);
		text-decoration: none;
	}

	.btn--hero:hover::after {
		width: 100%;
	}

	.text {
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		padding-right: 2rem;
	}
	.buttons {
		display: flex;
		gap: 1em;
	}
</style>
