<script>
  export let Name, Description, GitHubLink, WebsiteLink, OtherLink, OtherText;
</script>

<div class="projectCard">
  <span>
    <p class="projectName">{Name}</p>
    <p class="projectDesc">{Description}</p>
    <div class="links">
      {#if GitHubLink != undefined}
        <a href={GitHubLink} target="_blank">GitHub</a>
      {/if}
      {#if WebsiteLink != undefined}
        <a href={WebsiteLink} target="_blank">Website</a>
      {/if}
      {#if OtherLink != undefined}
        <a href={OtherLink} target="_blank">{OtherText}</a>
      {/if}
    </div>
  </span>
</div>

<style>
  .projectCard {
    display: block;
    height: 100%;
    margin: 1rem;
    position: relative;
    width: 90%;
  }

  .projectName {
    font-size: 1.125rem;
    color: #bb86fc;
  }

  .projectDesc {
    font-size: 1rem;
    color: #cecece;
  }

  a {
    color: #bb86fc;
    padding-right: 1rem;
  }

  a:hover {
    color: #e3cdff;
    text-decoration: underline;
  }
</style>
