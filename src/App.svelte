<script lang="ts">	
	import Navbar from "./Navbar.svelte"
	import githubIcon from "./assets/github.svg"

	import pixili from "./assets/projects/pixili.png"	
	import pentagon	 from "./assets/projects/pentagon.png"	
	import easytodo	 from "./assets/projects/easytodo.png"		
	import glsnake	 from "./assets/projects/glsnake.png"	
	import bombcakes	 from "./assets/projects/bombcakes.png"

	import Tools from "./Tools.svelte"	
	import planet from "./assets/planet.svg"
	import Footer from "./Footer.svelte"

const projects: {title: string; highlights: string[], content: string; image: string; link: string; github: string}[] = [
		{
			title: "Pixili",
			content: "My project, Pixili, is a browser based graphics creation software. The Highlights of my project are: ",
			highlights: ["cursor zooming", "recursive fill algorithm", "file saving"],
			image: pixili,
			link: "https://pixili.netlify.app",
			github: "https://github.com/FadedBronze/PixiliV2",
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
			github: "https://github.com/FadedBronze/pentagon.js",
		},
		{
			title: "GL-Snake",
			content: "A snake game written in c++ using a custom renderer:",
			highlights: [
				"3D",
				"top down left right movement",
				"built on top of opengl",
				"vibrant"
			],	
			image: glsnake,
			link: "https://github.com/FadedBronze/glsnake",
			github: "https://github.com/FadedBronze/glsnake",
		},
{
			title: "Bombcakes",
			content: "A game where you shoot at ghost hands. You don't want to be eaten!:",
			highlights: [
				"made using the rust programming language",
				"uses the bevy game framework",
				"menu system and collisions",
				"art all made by me"
			],	
			image: bombcakes,
			link: "https://github.com/FadedBronze/bombcakes",
			github: "https://github.com/FadedBronze/bombcakes",
		},
		{
			title: "Easy Todo",
			content: "A vscode task manager extension I made to solve my need to have todo notes inside vscode:",
			highlights: [
				"vscode extension",
				"trello-like task management",
				"free",
				"all your TODO's are stored in a json file with .eztodo file extension"
			],	
			image: easytodo,
			link: "https://marketplace.visualstudio.com/items?itemName=FadedBronze.easy-todo",
			github: "https://github.com/FadedBronze/.eztodo",
		},
	]
</script>


<main style="width:100%; display:flex; flex-direction:column; position:relative;overflow-x:hidden">	
	<Navbar></Navbar>	
	<div id="hero-section">
		<div id="hero-content" style="padding: 0 12vw;width:100%;">
			<p style="font-weight:500;">WEB DEVELOPER</p>	
			<h1 style="font-size: 50px;line-height: 95%;">Samyat Gautam</h1>
			<p style="margin-top:10px;width:60%">Hi, I am Samyat Gautam. I like to make games, websites, and tools, and learn about new technologies. On this page you'll find some of my finer works.</p>	
			<a href="#projects" style="text-decoration-line:none"><button class="button">Explore</button></a>	
		</div>
		<img src={planet} style="position:absolute; top:-10%; transform:scale(1.5); right:calc(-900px + 45vw)" alt="planet" />
	</div>
	<Tools></Tools>
	<div style="border-bottom: 2px solid black"></div>
	<div id="projects" style="display: flex; padding: 0 12vw; box-sizing:border-box; flex-direction:column; flex-wrap: wrap;gap: 60px; width: 100%">	
		<h2 style="font-size:50px;text-align:center;">Projects</h2>

		{#each projects as project} 
			<div class="project" style="display:flex; gap:20px; height:fit-content;">
				<div style="min-width:66%">
					<h3 style="font-size:37px;display:inline;">{project.title}</h3>
					<a href={project.github} target="_blank" style="display:inline;float:right">	
						<img src={githubIcon} alt="github icon"/>
					</a>	
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

	#hero-content button {
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
		gap: var(--page-spacing);
		padding: var(--page-spacing) 0;
	}

	@media only screen and (max-width: 500px) {	
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

		#hero-content p {
			width: 100% !important;
		}
	}
</style>
