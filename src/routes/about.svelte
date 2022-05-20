<style lang="scss">
	@import "./style/theme.scss";
	.about {
		position: fixed;
		top: 50%;
		left: 50%;
		text-align: center;
		transform: translate(-50%, -50%);
		width: 500px;

		h1	{
			color: $text-color;
			font-size: $about-h1-size;
			font-weight: bold;
		}

		p {
			color: $text-color;
			font-size: $about-p-size;
			margin: 8px;
		}
	}

</style>

<svelte:head>
	<title>About | muumi.xyz</title>
</svelte:head>

<div class="about">
	<h1>About Me!</h1>

	<p>Hi!</p>
	<p>My name is muumi or muumif.</p>
	<p>My first programs were written in 2017 and I have been making projects ever since.</p>
	<p>I started out with Unity and C#. In the past two years I have been working with Javascript.</p>
	<p>Also at the time I was learning Javascript I started to take interest in servers and Linux.</p>
	<p>Right now I host my own services on my home server and i also maintain a Discord Bot.</p>
</div>