<script>
	import { onMount } from 'svelte';
	import gsap from 'gsap';

	let open = false;
	let sidebar;
	let sidebarWrapper;
	let linksContainer;

	function toggleMenu() {
		open = !open;
		animatePaths(open);
		setOpenState(open);
	}

	function setOpenState(isOpen) {
		open = isOpen;
		const radius = Math.ceil(window.innerHeight * 1.1);
		if (open) {
			gsap.to(sidebar, {
				clipPath: `circle(${radius}px at 50px 50px)`,
				duration: 0.5,
				ease: 'power4.out'
			});
			animateLinksIn();
		} else {
			gsap.to(sidebar, {
				clipPath: 'circle(25px at 2.5em 2.5em)',
				duration: 0.5,
				ease: 'power4.in'
			});
			animateLinksOut();
		}
	}

	function handleClickOutside(event) {
		if (open && !sidebar.contains(event.target) && !event.target.closest('.menu-toggle')) {
			setOpenState(false);
			animatePaths(false);
		}
	}

	function animatePaths(isOpen) {
		const topPath = document.getElementById('topPath');
		const middlePath = document.getElementById('middlePath');
		const bottomPath = document.getElementById('bottomPath');

		if (isOpen) {
			gsap.to(topPath, { y: 0, rotation: 45, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 0, duration: 0.1 });
			gsap.to(bottomPath, { y: 0, rotation: -45, duration: 0.3, ease: 'power2.out' });
		} else {
			gsap.to(topPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
			gsap.to(middlePath, { opacity: 1, duration: 0.1, delay: 0.2 });
			gsap.to(bottomPath, { y: 0, rotation: 0, duration: 0.3, ease: 'power2.out' });
		}
	}

	function animateLinksIn() {
		if (linksContainer && linksContainer.querySelectorAll) {
			const linkElements = linksContainer.querySelectorAll('.link');
			gsap.fromTo(
				linkElements,
				{ y: 30, opacity: 0 },
				{ y: 0, opacity: 1, stagger: 0.05, duration: 0.2, ease: 'power2.in' }
			);
		}
	}

	function animateLinksOut() {
		if (linksContainer && linksContainer.querySelectorAll) {
			const linkElements = linksContainer.querySelectorAll('.link');
			gsap.to(linkElements, {
				y: 50,
				opacity: 0,
				stagger: -0.1,
				duration: 0.1,
				ease: 'power2.in'
			});
		}
	}

	function addLinkHoverEffects() {
		const linkElements = linksContainer.querySelectorAll('.link');

		linkElements.forEach((link) => {
			link.addEventListener('mouseenter', () => {
				gsap.to(link, { scale: 1.1, duration: 0.2, ease: 'power2.out' });
			});
			link.addEventListener('mouseleave', () => {
				gsap.to(link, { scale: 1, duration: 0.2, ease: 'power2.out' });
			});
			link.addEventListener('mousedown', () => {
				gsap.to(link, { scale: 0.95, duration: 0.1, ease: 'power2.in' });
			});
			link.addEventListener('mouseup', () => {
				gsap.to(link, { scale: 1.1, duration: 0.1, ease: 'power2.out' });
			});
		});
	}

	onMount(() => {
		gsap.set(sidebar, { clipPath: 'circle(25px at 2.5em 2.5em)' });
		document.addEventListener('click', handleClickOutside);
		addLinkHoverEffects();

		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<div class="sidebar-wrapper" bind:this={sidebarWrapper}>
	<div bind:this={sidebar} class="sidebar">
		<div class="links" bind:this={linksContainer}>
			<a href="/" class="link">Home</a>
			<a href="/aboutme" class="link">About Me</a>
			<a href="/projects" class="link">Projects</a>
			<a href="/skills" class="link">Skills</a>
			<a href="/contact" class="link">Contact</a>
			<a href="/hobbies" class="link">Hobbies And Interests</a>
		</div>
	</div>
	<button class="menu-toggle" on:click={toggleMenu}>
		<svg width="23" height="23" viewBox="0 0 23 23">
			<path
				id="topPath"
				stroke-width="3"
				stroke="#a6e3a1"
				stroke-linecap="round"
				d="M 2 2.5 L 20 2.5"
			/>
			<path
				id="middlePath"
				stroke-width="3"
				stroke="#a6e3a1"
				stroke-linecap="round"
				d="M 2 9.423 L 20 9.423"
			/>
			<path
				id="bottomPath"
				stroke-width="3"
				stroke="#a6e3a1"
				stroke-linecap="round"
				d="M 2 16.346 L 20 16.346"
			/>
		</svg>
	</button>
</div>

<style>
	.sidebar-wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.sidebar {
		z-index: 999;
		position: fixed;
		top: 0;
		left: 0;
		bottom: 0;
		width: 400px;
		background: #181825;
	}
	.menu-toggle {
		z-index: 999;
		position: fixed;
		width: 50px;
		height: 50px;
		border-radius: 50%;
		top: 18px;
		left: 9px;
		padding-left: 15px;
		border: none;
		cursor: pointer;
		background: none;
	}
	.links {
		position: absolute;
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		gap: 5%;
	}
	.link {
		font-size: 25px;
		color: #bac2de;
		text-decoration: none;
	}
</style>
