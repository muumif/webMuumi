<script>

</script>

<style lang="scss">
	@import "./style/theme.scss";
	.projects {
		position: fixed;
		top: 50%;
		left: 50%;
		text-align: center;
		transform: translate(-50%, -50%);

		.card {
			background: #fff;
			border-radius: 15px;
			border-color: transparent;
			border-style: solid;
			display: inline-block;
			height: 300px;
			margin: 1rem;
			position: relative;
			width: 250px;
			box-shadow: 8px 12px $card-shadow-color;

			h3 {
				color: $text-color;
				font-weight: bold;
				font-size: $card-title-size;
				padding-top: 10px;
			}

			p {
				color: $text-color;
				font-size: $card-desc-size;
				margin-bottom: 4px;
			}

			a {
				color: $main-color;
				margin: 5px;
				text-decoration: none;
			}

			a:hover {
				text-decoration: underline;
			}
		}
	}
</style>

<svelte:head>
	<title>Project | muumi.xyz</title>
</svelte:head>

<div class="projects">
	<div class="card">
		<span>
			<img src="http://images.muumi.xyz/muumi.xyz/projects/EdgyLoba.png" alt="EdgyLoba.png" width="120" height="120"/>
			<h3>EdgyLoba</h3>
			<p>A Discord Bot for checking Apex Legends stats and used for much more.</p>
			<a href="https://github.com/muumif/Edgy-Loba">Github</a>
			<a href="https://discord.com/oauth2/authorize?client_id=719542118955090011&scope=bot">Bot Invite</a>
			<a href="https://top.gg/bot/719542118955090011">Top.gg</a>
		</span>
	</div>
	<div class ="card">
		<span>
			<img src="http://images.muumi.xyz/muumi.xyz/projects/mto.png" alt ="mto.png" width="120" height="120">
			<h3>MTO</h3>
			<p>Website that gets MyAnimeList animes then searches them from osu! api.</p>
			<a href="https://mto.muumi.xyz">Website</a>
		</span>
	</div>
</div>