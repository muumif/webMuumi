<script>

</script>

<style lang="scss">
	@import "./style/theme.scss";
	.main {
		position: fixed;
		top: 50%;
		left: 50%;
		-webkit-transform: translate(-50%, -50%);
		transform: translate(-50%, -50%);

		h1 {
			color: $text-color;
			font-weight: bold;
			font-size: $main-h1-size;
			text-align: center;
		}
	
		a {
			color: $text-color;
			font-size: $main-a-size;
			margin: $main-a-spacing;
			text-decoration: none;
		}

		p {
			color: $text-color;
			text-align: center;
			font-size: $main-p-size;
			margin-top: -25px;
			margin-bottom: 5px;
		}
	}
</style>

<svelte:head>
	<title>Home | muumi.xyz</title>
</svelte:head>

<div class="main">
	<h1>muumi</h1>
	<p>Personal website!</p>
	<a href="about">About</a>
	<a href="projects">Projects</a>
	<a href="https://github.com/muumif">Github</a>
</div>

