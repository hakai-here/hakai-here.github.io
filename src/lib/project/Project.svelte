<script>
    import board from "../../assets/board.svg";
</script>
<section class="container4" id="works">
    <div class="left4">
        The lion's share of the tasks I worked on were  personal or group
        projects ranging from web apps to shell applications. It was a fun
        journey learning different technologies, discovering bugs and logical
        errors, debugging them, deleting, restarting from scratch, and finishing
        them with satisfaction.
        <br /><br />
        This website, built in Svelte and heavily influenced by doddle animations,
        is one of my all-time favorites. In addition, I'm currently working on <a href="https://github.com/simple-svelte-ui">simple-svelte-ui</a>,
        a svelte component library. Not to mention <a href="https://github.com/d8rkmind/Pyosint"> Pyosint </a> and <a href="https://github.com/d8rkmind/T1T5">T1T5</a>, two projects
        on which I collaborated with a fantastic team, and the list goes on.
    </div>
    <div class="right4">
        <span class="middle4">More on Github</span>
        <a href="https://github.com/d8rkmind?tab=repositories"><img draggable="false" class="img4" src={board} alt="" /></a>
    </div>
</section>

<style>
    .container4 {
        padding: 2em 10em;
        display: flex;
        flex-direction: row;
    }
    .left4 {
        flex: 1;
        font-size: 30px;
        text-align: justify;
    }
    .left4 a{
        text-decoration: none;
        color: rgb(196, 52, 52);
    }
    
    .right4 {
        flex: 1;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }
    .img4 {
        height: 15em;
        cursor: pointer;
    }
    .middle4{
        position: absolute;
        font-size: 40px;
        margin-left: -1em;
        cursor: pointer;
        color: rgb(196, 52, 52);
        z-index: -1;
    }


    @media screen and (max-width: 1500px){
        .container4 {
            flex-direction: column;
        }
    }
    @media screen and (max-width: 1100px) {
        .container4 {
            padding: 0 3em;
            flex-direction: column;
        }
        .img4 {
        height: 6em;
        }
        .middle4{
            font-size: 15px;
        }
        .left4{
            text-align: center;
        }
    }
</style>
