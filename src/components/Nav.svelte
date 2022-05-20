<script>
	export let segment;
</script>

<style lang="scss">
	@import "./style/theme.scss";

	ul {
		margin: 0;
		padding: 0;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: block;
		float: left;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: $text-color;
		display: block;
		bottom: -1px;

	}

	a {
		font-size: $nav-buttons-size;
		color: $text-color;
		text-decoration: none;
		padding: 1em 0.5em;
		padding-bottom: 2px;
		display: block;
	}
</style>

<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">Home</a></li>
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">About</a></li>
		<li><a aria-current="{segment === 'projects' ? 'page' : undefined}" href="projects">Projects</a></li>

	</ul>
</nav>
