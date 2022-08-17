<script>
    import Navbar from "./lib/nav/Navbar.svelte";
    import Hero from "./lib/hero/Hero.svelte";
 
    import About from "./lib/about/About.svelte";
    import circle from "./assets/circle.svg";
    import { fade } from "svelte/transition";
    import { onMount } from "svelte";
    let pageloaded = false;
    onMount(() => {
        setTimeout(() => {
            pageloaded = true;
            window.scroll(0, 0);
        }, 2000);
    });

   
    import Project from "./lib/project/Project.svelte";
</script>

{#if !pageloaded}
    <div class="loader" in:fade out:fade>
        <img src={circle} alt="" />
    </div>
{/if}

<div>
    <Navbar />
    <main id="home">
        <Hero />
        <About />
        <Project />
    </main>
</div>

<style>
    .loader {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 9999;
        display: grid;
        place-items: center;
        background-color: #fff;
    }
    .loader img {
        height: 20vh;
        animation: rotation 2s infinite linear;
    }
    main {
        padding-top: 60px !important;
    }
    
    @keyframes rotation {
        from {
            transform: rotate(360deg);
        }
        to {
            transform: rotate(1deg);
        }
    }
   
</style>
