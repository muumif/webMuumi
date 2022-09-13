<script>
    import { createEventDispatcher, onDestroy} from "svelte";

    const dispatch = createEventDispatcher();
    const close = () => dispatch("close");

    let modal;

    const handle_keydown = e => {
        if (e.key === "Escape") {
            close();
            return;
        }
        if (e.key === 'Tab') {
            // trap focus
            const nodes = modal.querySelectorAll('*');
            const tabbable = Array.from(nodes).filter(n => n.tabIndex >= 0);

            let index = tabbable.indexOf(document.activeElement);
            if (index === -1 && e.shiftKey) index = 0;

            index += tabbable.length + (e.shiftKey ? -1 : 1);
            index %= tabbable.length;

            tabbable[index].focus();
            e.preventDefault();
        }
    };

    const previously_focused = typeof document !== 'undefined' && document.activeElement;

    if (previously_focused) {
        onDestroy(() => {
            previously_focused.focus();
        });
    }
</script>

<svelte:window on:keydown={handle_keydown}/>

<div class="modal-background" on:click={close}></div>

<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
    <h1 class="text-center text-xl font-bold">Projects</h1>
    <p class="text-center text-sm">All my public projects!</p>
    <slot name="header"></slot>
    <hr>
    <slot></slot>
    <hr>

    <!-- svelte-ignore a11y-autofocus -->
    <button autofocus on:click={close} class="text-left pt-3 font-bold text-xl">Close</button>
</div>

<style>
    .modal-background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        backdrop-filter: blur(4px);
        -webkit-backdrop-filter: blur(4px);
    }
    h1 {
        animation-name: color_change;
        animation-duration: 3s;
        animation-iteration-count: infinite;
        animation-direction: alternate;
        color: #BB86FC;
    }

    @keyframes color_change {
        0% { color: #9400D3; }
        25% { color: #0000FF; }
        50% { color: #00FF00;}
        75% {color: #FFFF00; }
        100% { color: #FF0000; }
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
        transform: translate(-50%,-50%);
        padding: 1em;
        border-radius: 0.2em;
        background: #121212;
    }

    button {
        display: block;
        color: #CF6679;
    }

    button:hover {
        color: #de344c;
    }
</style>