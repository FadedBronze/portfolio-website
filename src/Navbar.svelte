<script lang="ts">
	import folderIcon from "./assets/folder.svg"
	import homeIcon from "./assets/home.svg"
	import githubIcon from "./assets/github.svg"


	const links: {src: string; alt: string; href: string}[] = [
		{
			src: folderIcon,
			alt: "folderIcon",
			href: "#projects"
		},
		{
			src: homeIcon,
			alt: "homeIcon",
			href: "#hero-section"
		},
		{
			src: githubIcon,	
			alt: "githubIcon",
			href: "https://github.com/fadedbronze"
		}
	]
</script>

<nav id="navbar">
		{#each links as link}
			<a href={link.href}>
				<img src={link.src} alt={link.alt}/>
			</a>	
		{/each}	
</nav>

<style>
	#navbar {
		flex-grow: 0;
		display: flex;
		justify-content: left;
		width: 100%;	
		padding: 0 12vw;	
		gap: 16px;
	}

	#navbar a {	
		width: 30px;
		height: 30px;
		display: flex;
		justify-content: center;
		align-items: center;	
		display: flex;
	}

	#navbar img {
		display: block;
		max-width: 70%;
	}

	@media only screen and (max-width: 500px) {
		#navbar {
			justify-content: left;
		}
	}
</style>
