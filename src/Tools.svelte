<script lang="ts">
	import excalidraw from "./assets/tools/excalidraw.png"
	import figma from "./assets/tools/figma.png"
	import neovim from "./assets/tools/neovim.png"
	import nextjs from "./assets/tools/nextjs.png"	
	import postgresql from "./assets/tools/postgresql.png"	
	import react from "./assets/tools/react.png"
	import rust from "./assets/tools/rust.png"
	import svelte from "./assets/tools/svelte.png"
	import typescript from "./assets/tools/typescript.png"
	import express from "./assets/tools/express.png"
</script>

<div id="tools" style="display:flex; flex-wrap:wrap; justify-content: start; gap: 25px; padding: 0 12vw;">
	<a href="https://excalidraw.com/" target="_blank">
		<img src={excalidraw} alt="excalidraw icon" />	
	</a>
	<a href="https://figma.com/" target="_blank">
		<img src={figma} alt="figma icon" />	
	</a>
	<a href="https://neovim.io/" target="_blank">
		<img src={neovim} alt="neovim icon" />	
	</a>	
	<a href="https://nextjs.org/" target="_blank">
		<img src={nextjs} alt="nextjs icon" />	
	</a>	
	<a href="https://www.postgresql.org/" target="_blank">
		<img src={postgresql} alt="postgresql icon" />	
	</a>	
	<a href="https://react.dev/" target="_blank">
		<img src={react} alt="react icon" />	
	</a>	
	<a href="https://www.rust-lang.org/" target="_blank">
		<img src={rust} alt="rust icon" />	
	</a>	
	<a href="https://svelte.dev/" target="_blank">
		<img src={svelte} alt="svelte icon" />
	</a>	
	<a href="https://www.typescriptlang.org/" target="_blank">
		<img src={typescript} alt="typescript icon" />	
	</a>	
	<a href="https://expressjs.com/" target="_blank">
		<img src={express} alt="express icon" />	
	</a>	
</div>

<style>
	#tools img {
		transform: scale(0.3);
	}	

	#tools a {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 50px;
		height: 50px;
	}

	@media only screen and (max-width: 500px) {
		#tools {
			justify-content: space-around !important;
		}	

		#tools img {
			transform: scale(0.2);
		}

		#tools a {
			display: flex;
			justify-content: center;
			align-items: center;
			width: 30px;
			height: 30px;
		}
	}
</style>
