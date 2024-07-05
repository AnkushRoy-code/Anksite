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
			</div>
			<img src="/gameOfLife.webp" alt="" />
		</div>
	</section>
	<section id="eco" class="EcoSight">
		<div class="container">
			<div>
				<h1>Ecosight</h1>
				<p>
					This project, developed by my team and me during a GeeksForGeeks hackathon. We created an
					innovative application that provides analytical insights through an intuitive online
					interface. Our work focused on environmental concerns, featuring analyses such as carbon
					footprint assessment and satellite image classification.
				</p>
			</div>
			<img src="/ecosight.webp" alt="" />
		</div>
	</section>
	<section id="particle" class="ParticleLife">
		<div class="container">
			<div>
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
			</div>
			<img src="/particle.webp" alt="" />
		</div>
	</section>
	<section id="stream" class="StreamerHub">
		<div class="container">
			<div>
				<h1>Streamer Hub</h1>
				<p>
					I developed StreamerHub, a frontend application using React and GSAP. StreamerHub serves
					as a professional hub for streamers, featuring a sleek and interactive user interface. The
					application focuses on providing a seamless experience for users to manage and showcase
					their streaming content effectively. With React's framework and GSAP's animation
					capabilities, StreamerHub delivers a dynamic and visually engaging platform tailored for
					streamers and their audiences.
				</p>
			</div>
			<img src="/stream.webp" alt="" />
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
</style>
