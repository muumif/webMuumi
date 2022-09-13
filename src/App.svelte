<script>
  import Links from "./lib/Links.svelte";
  import Footer from "./lib/Footer.svelte";
  import Card from "./lib/Card.svelte";
</script>

<svelte:head>
  <title>muumi</title>
  <html lang="en" />
</svelte:head>

<main>
  <div class="flex h-screen">
    <div class="m-auto">
      <h1 class="text-center font-semibold text-6xl tracking-wide">muumi</h1>
      <p class="text-center font-normal text-2xl tracking-wide py-3">Student & Programmer</p>
      <Links />
    </div>
  </div>
</main>
<Footer />

<style>
  :global(body, html) {
    background-image: url("./assets/Sprinkle.svg");
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    background-position: center;
    image-rendering: crisp-edges;
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
    margin: 0;
    height: 100%;
    overflow: hidden;
  }
  h1 {
    animation-name: color_change;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    color: #BB86FC;
  }
  p {
    color: #cecece;
  }
  @keyframes color_change {
    0% { color: #e2bdff; }
    50% { color: #ba82ff;}
    100% { color: #8f00ff; }
  }
</style>
