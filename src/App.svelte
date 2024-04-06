<script lang="ts">	
	import {onMount} from "svelte"
	import Navbar from "./Navbar.svelte"
	import githubIcon from "./assets/github.svg"
	import pixili from "./assets/pixili.png"	
	import pentagon	 from "./assets/pentagon.png"
	import Tools from "./Tools.svelte"	
	import planet from "./assets/planet.svg"
	import Footer from "./Footer.svelte"

	let wheelOffset = 0
	let maxScroll = 0
	const windowWidth = window.innerWidth	
	const windowHeight = window.innerHeight

	onMount(() => {
		maxScroll = window.innerHeight

		window.addEventListener("scroll", () => {
			wheelOffset = window.scrollY 

			if (wheelOffset > 1400) {
				console.log("hi")	
			}
		})	
	})	

	const projects: {title: string; highlights: string[], content: string; image: string; link: string; github: string}[] = [
		{
			title: "Pixili",
			content: "My project, Pixili, is a browser based graphics creation software. The Highlights of my project are: ",
			highlights: ["cursor zooming", "recursive fill algorithm", "file saving"],
			image: pixili,
			link: "https://pixili.netlify.app",
			github: "",
		},
		{
			title: "Pentagon",
			content: "A physics simulation supporting:",
			highlights: [
				"Both polygon and circle collision", 
				"convex polygon and circle rigidbodies",
				"Velocity Collision Resolution using Separating Axis Theorem",
				"Friction"
			],	
			image: pentagon,
			link: "https://fadedbronze.github.io/pentagon.js/",
			github: "",
		}	
	]
</script>


<main style="width:100%; display:flex; flex-direction:column; padding: 50px 0; position:relative;overflow-x:hidden">	
	<Navbar></Navbar>	
	<div id="hero-section">
		<div id="hero-content" style="padding: 0 12vw;width:100%;">
			<p style="font-weight:500;">WEB DEVELOPER</p>	
			<h1 style="font-size: 50px;line-height: 95%;">Samyat Gautam</h1>
			<p style="margin-top:10px;width:60%">Really bad fix! Hi, I’m Samyat. I have a fondness for niche technological subjects. Love creating graphical applications or anything with visuals. Prepared to bring a new perspective to any collaborative en devours. Web developer with expertise in HTML canvas.</p>	
			<button>Explore</button>	
		</div>
		<img src={planet} style="position:absolute; top:-10%; transform:scale(1.5); right:calc(-900px + 45vw)" alt="planet" />
	</div>
	<Tools></Tools>
	<div style="border-bottom: 2px solid black;"></div>
	<div id="projects" style="display: flex; padding: 0 12vw; box-sizing:border-box; flex-direction:column; flex-wrap: wrap;gap: 60px; width: 100%">	
		<h2 style="font-size:50px;text-align:center;">Projects</h2>

		{#each projects as project} 
			<div class="project" style="display:flex; gap:20px; height:fit-content;">
				<div style="min-width:66%">
					<h3 style="font-size:37px;display:inline;">{project.title}</h3>
					<img src={githubIcon} style="display:inline;float:right" alt="github icon"/>
					<p style="word-break:keep-all">{project.content}</p>
					<ul>
						{#each project.highlights as highlight}
							<li>{highlight}</li>
						{/each}
					</ul>
				</div>
				<a target="_blank" href={project.link} style="border:1px solid var(--color-primary-faded); flex-grow: 1; border: 4px solid var(--color-primary); border-radius: 20px; overflow: hidden;">
					<img src={project.image} alt="project image" style="display:block;width:100%;height:100%;object-fit:cover;object-position:right;" />
				</a>
			</div>
		{/each}	
	</div>
	<Footer></Footer>
</main>

<style>		

	#hero-content > button {
		margin-top: 30px;
		padding: 20px 25px;
		border-radius: 20px;
		border: 0;
		background-color: var(--color-primary);
		color: var(--color-headers);
		font-weight: 700;
	}

	#hero-section {
		flex-grow: 1;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	main {
		gap: 150px;
	}

	@media only screen and (max-width: 500px) {
		main {
			gap: 50px;
		}	

		#hero-section {
			justify-content: start;
			box-sizing: border-box;
		}

		#hero-content {
			text-align: start !important;
		}
	

		#projects h2 {	
			font-size: 37px !important;
		}	
			
		.project h3 {
			font-size: 28px !important;
		}
	}

	@media only screen and (max-width: 800px) {
		.project {
			flex-wrap: wrap;
		}

		#hero-section img {
			display: none;
		}

		main {
			gap: 75px;
		}

		#hero-content p {
			width: 100% !important;
		}
	}
</style>
