<script>
    import { fade, fly } from "svelte/transition";
    import linkedin from "../../assets/linkedin.svg";
    import github from "../../assets/github.svg";
    import twitter from "../../assets/twitter.svg";
    import mail from "../../assets/mail.svg";
    import popupghost from "../../assets/popupghost.svg";
    let show = false;
    let showmsg = false;
    function showanim() {
        showmsg = true;
        navigator.clipboard.writeText("syamsv01@gmail.com");
        setTimeout(() => {
            showmsg = false;
        }, 1000);
    }
    function loadScroll() {
        show = true;
        console.log(show);
    }
    function removeScroll() {
        show = false;
        console.log(show);
    }
    function scrollto({target}){
		const el = document.querySelector(target.getAttribute("href"));
		if (!el) return;
		el.scrollIntoView({behavior: "smooth"});
	}
</script>

<footer on:mouseenter={loadScroll} on:mouseleave={removeScroll}>
    <div class="fleft">
        <ul>
            <li href="#home" on:click={scrollto}>Home</li>
            <li href="#about" on:click={scrollto}>About</li>
			<li href="#works" on:click={scrollto}>Works</li>
            <a href="https://github.com/d8rkmind/public/raw/main/data/Syam_SV_Resume.pdf"><li>Resume</li></a>
        </ul>
    </div>
    <div class="fright">
        {#if show}
            <img draggable="false"
                in:fly={{ y: 100, duration: 500 }}
                out:fly={{ y: -100, duration: 500 }}
                src={popupghost}
                alt=""
                class="popupghost"
            />
        {/if}
    </div>
    <div class="fmiddle">
        <ul>
            <li>
                <a href="https://linkedin.com/in/syam-sv-7b411a242">
                    <img
                        draggable="false"
                        src={linkedin}
                        alt="Linkedin"
                        class="img5"
                    /></a
                >
            </li>
            <li>
                <a href="https://github.com/d8rkmind">
                    <img
                        draggable="false"
                        src={github}
                        alt="Github"
                        class="img5"
                    />
                </a>
            </li>
            <li>
                <a href="https://twitter.com/SyamSv">
                    <img
                        draggable="false"
                        src={twitter}
                        alt="Twitter"
                        class="img5"
                    /></a
                >
            </li>
            <li class="mail">
                <img
                    draggable="false"
                    src={mail}
                    alt="Github"
                    class="img5"
                    on:click={showanim}
                />
                {#if showmsg}
                    <span
                        in:fly={{ y: 200, duration: 600 }}
                        out:fade
                        class="footerc">copied to clipboard</span
                    >
                {/if}
            </li>
        </ul>
    </div>
</footer>

<style>
    footer {
        height: 40vh;
        padding: 5em 10em;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
    .fleft,
    .fright,
    .fmiddle {
        flex: 1;
    }
    .fleft ul {
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .fleft a{
        text-decoration: none;
        color: #000;
    }
    .fleft li {
        margin: 0 1em;
        font-size: 20px;
        cursor: pointer;
        transition: color 0.5s ease;
    }
    .fright {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .fmiddle ul {
        list-style: none;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .fmiddle li {
        margin: 0 1em;
        font-size: 20px;
        cursor: pointer;
    }
    .fleft li:hover{
        color: rgb(196, 52, 52);
    }
    .popupghost {
        height: 15em;
    }
    .img5 {
        height: 2em;
    }
    .mail {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .footerc {
        position: absolute;
        margin-top: -5em;
        font-size: 12px;
    }
    @media screen and (max-width: 1100px) {
        footer {
            padding: 5em 1em;
        }
        .fleft ul {
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .fleft li {
            margin: 0.5em 0;
        }
        .fmiddle ul {
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .fmiddle li {
            margin: 0.5em 0;
        }
        .popupghost{
            height: 7.5em;
        }
    }
</style>
