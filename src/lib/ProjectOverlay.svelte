<script>
  import { createEventDispatcher, onDestroy } from "svelte";

  const dispatch = createEventDispatcher();
  const close = () => dispatch("close");

  let modal;

  const handle_keydown = (e) => {
    if (e.key === "Escape") {
      close();
      return;
    }
    if (e.key === "Tab") {

      const nodes = modal.querySelectorAll("*");
      const tabbable = Array.from(nodes).filter((n) => n.tabIndex >= 0);

      let index = tabbable.indexOf(document.activeElement);
      if (index === -1 && e.shiftKey) index = 0;

      index += tabbable.length + (e.shiftKey ? -1 : 1);
      index %= tabbable.length;

      tabbable[index].focus();
      e.preventDefault();
    }
  };

  const previously_focused =
    typeof document !== "undefined" && document.activeElement;

  if (previously_focused) {
    onDestroy(() => {
      previously_focused.focus();
    });
  }
</script>

<svelte:window on:keydown={handle_keydown} />

<div class="modal-background" on:click={close} />

<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
  <slot name="header" />
    <h1 class="text-center text-xl font-bold">Projects</h1>
    <p class="text-center text-sm pb-3">All my public projects!</p>
    <hr />
  <slot />


  <slot name="footer">
    <hr />

    <button autofocus on:click={close} class="footer-close"
      >Close</button
    >
  </slot>
</div>

<style>
  .modal-background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(4px);
  }
  h1 {
    animation-name: color_change;
    animation-duration: 3s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    color: #bb86fc;
  }

  @keyframes color_change {
    0% {
      color: #9400d3;
    }
    25% {
      color: #0000ff;
    }
    50% {
      color: #00ff00;
    }
    75% {
      color: #ffff00;
    }
    100% {
      color: #ff0000;
    }
  }
  p {
    color: #cecece;
  }
  .modal {
    position: absolute;
    left: 50%;
    top: 50%;
    width: calc(100vw - 4em);
    max-width: 32em;
    max-height: calc(100vh - 4em);
    overflow: auto;
    transform: translate(-50%, -50%);
    padding: 1em;
    border-radius: 0.3rem;
    border-color: #8a8989;
    border-width: 2px;
    background: #121212;
  }

  button {
    color: #cf6679;
  }

  button:hover {
    color: #de344c;
  }

  .footer-close {
    text-align: center;
    margin: 0 auto;
    font-weight: bold;
    font-size: 1.25rem;
    line-height: 1.75rem;
    padding-top: 2rem;
    width:100px; 
    margin: -20px -50px; 
    position:relative;
    left:50%;
  }
</style>
