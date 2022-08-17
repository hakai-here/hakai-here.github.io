<script>
    import App from "./App.svelte";
    import mouse from "./assets/mouse.svg";
    import Footer from "./lib/footer/Footer.svelte";
    let x = window.innerWidth / 2;
    let y = window.innerHeight / 3;
    function Handlemouse(event) {
        x = event.clientX;
        y = event.clientY;
    }

    const device =
        /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
            navigator.userAgent
        );
</script>
<div class="wrap" on:mousemove={Handlemouse}>
{#if !device}
        <div class="trail" style="transform: translate({x}px, {y}px)">
            <img src={mouse} alt="" class="mouseimg" />
        </div>
{/if}
<App/>
<Footer/>
</div>
<style>
    .wrap {
        width: 100%;
        height: 100%;
    }
    @media (hover: hover) and (pointer: fine) {
        .trail {
            z-index: 99;
            position: fixed;
            left: 0;
            top: 0;
            pointer-events: none;
            will-change: transform;
            transition: transform 0.1s ease-out;
        }
        .trail .mouseimg {
            height: 5vw;
        }
    }
</style>