<script lang="ts">

</script>

<main style="width:100vw;height:100vh;display:flex;flex-direction:column;">
	<nav id="navbar">
		<div id="navbar-island">
			<a href="#">
				<img src="#"/>
			</a>
			<a href="#">
				<img src="#"/>
			</a>
			<a href="#">
				<img src="#"/>
			</a>
		<div>
		</nav>
	<div id="hero-section">
		<div id="hero-content">
			<p style="font-weight:500;">WEB DEVELOPER</p>	
			<h1>Im Samyat Gautam</h1>
			<p style="margin-top:10px;">Really bad fix! Hi, I’m Samyat. I have a fondness for niche technological subjects. Love creating graphical applications or anything with visuals. Prepared to bring a new perspective to any collaborative en devours. Web developer with expertise in HTML canvas.</p>	
		</div>
	</div>
</main>

<style>	
	#navbar {
		flex-grow: 0;
		display: flex;
		justify-content: center;
		width: 100%;
	}

	#navbar-island {
		width: fit-content;
		box-content: border-box;
		padding: 12px;
		display: flex;
		gap: 16px;
	}

	#navbar a {
	}

	#navbar img {
		display: block;
		max-width: 100%;
	}

	#hero-content > h1 {
		font-size: 50px;
	}

	#hero-content > p {
		font-size: 16px;
	}

	#hero-section {
		flex-grow: 1;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	#hero-content {
		width: calc(66%);
		text-align: center;
	}
</style>
