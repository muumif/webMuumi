<script>
  import ProjectOverlay from "./ProjectOverlay.svelte";
  import Card from "./Card.svelte";

  let showModal = false;
</script>

<div>
  <a href="https://github.com/muumif" target="_blank">GitHub</a>
  <a href="https://twitter.com/TTV_Muumi" target="_blank">Twitter</a>
  <a on:click={() => (showModal = true)} href="#">Projects</a>
  <a href="https://steamcommunity.com/id/muumif/" target="_blank">Steam</a>
  <a href="https://www.twitch.tv/muumif" target="_blank">Twitch</a>
</div>

{#if showModal}
  <ProjectOverlay on:close={() => (showModal = false)}>
    <Card
      Name="muumi.xyz"
      Description="This website!"
      WebsiteLink="https://muumi.xyz"
      GitHubLink="https://github.com/muumif/webMuumi"
    />
    <Card
            Name="mto.muumi.xyz"
            Description="Website that gets MyAnimeList animes then searches them from osu! api and gets the songs for those animes!"
            WebsiteLink="https://mto.muumi.xyz"
    />
    <Card
      Name="Edgy Loba"
      Description="A simple Apex Legends stats checker aimed at ranked players. User linking, Graphs, Map Rotation, Leaderboard and more."
      GitHubLink="https://github.com/muumif/Edgy-Loba"
      OtherLink="https://bit.ly/edgylobainvite"
      OtherText="Invite"
    />
    <Card
      Name="IT22E-Bot"
      Description="A simple Discord Bot for checking my school timetable also includes a reminder when a lesson starts."
      GitHubLink="https://github.com/muumif/IT-22E-Bot"
    />
  </ProjectOverlay>
{/if}

<style>
  a {
    padding-right: 20px;
    font-size: 20px;
    line-height: 26px;
    color: #bb86fc;
    display: inline-block;
    position: relative;
  }

  a:after {
    content: "";
    position: absolute;
    width: calc(100% - 19px);
    transform: scaleX(0);
    height: 3px;
    bottom: 0;
    left: 0;
    background-color: #8a8989;
    transform-origin: bottom right;
    transition: transform 0.25s ease-out;
    animation-name: color_change;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
  }

  a:hover:after {
    transform: scaleX(1);
    transform-origin: bottom left;
  }

  @keyframes color_change {
    0% {
      background-color: #e2bdff;
    }
    50% {
      background-color: #ba82ff;
    }
    100% {
      background-color: #8f00ff;
    }
  }
</style>
