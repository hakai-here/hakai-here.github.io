<script>
    import think from "../../assets/think.svg";
    const array = [
        "HTML",
        "Css",
        "Javascript",
        "Typescript",
        "Svelte",
        "React",
        "Python",
        "Node Js",
        "Java",
        "C++",
        "Go",
        "Blender",
        "Git",
        "Sass",
        "npm",
        "Yarn",
        "SQL",
        "Tauri",
        "Electron",
    ];
    const num = array.length;
    let index = 0;
    let value;
    setInterval(function () {
        value = array[index];
        index = (index + 1) % num;
    }, 1000);
</script>

<section class="container3">
    <div class="left3">
        <span class="middle3">{value}</span>
        <img draggable="false" src={think} alt="" />
    </div>
    <div class="right3">
        So, once again, I'm Syam SV, a self-taught and motivated developer
        bringing you programming and design just for fun. I have experience
        developing web and desktop applications(web technology), including front-end and
        back-end development.<br /><br /> I am currently in India, where I'm at VIT
        Bhopal pursuing a B.Tech in cybersecurity and digital forensics. I am fascinated
        by 3D effects, animations, and the creation of intuitive, dynamic user experiences.
        I'm interested in the entire web and 3D world and enjoy working on challenging
        projects with positive people.
    </div>
</section>

<style>
    .container3 {
        padding: 3em 10em;
        display: flex;
        flex-direction: row;
    }
    /* .right3{
        width: 50%;
        padding: 2em;
        border-radius: 10px;
        background-color: #f5f5f5;
        box-shadow: 0px 0px 10px #ccc;
    } */
    .left3 {
        overflow: hidden;
        flex: 1;
        background-repeat: no-repeat;
        background-size: contain;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .middle3 {
        position: absolute;
        font-size: 50px;
        z-index: -1;
        margin-top: -2em;
    }
    .left3 img {
        height: 32em;
    }
    .right3 {
        font-size: 30px;
        text-align: justify;
        flex: 1;
    }
    @media screen and (max-width: 1500px){
        .container3 {
            flex-direction: column;
        }
    }
    @media screen and (max-width: 1100px) {
        .container3 {
            padding: 2em 3em;
            flex-direction: column;
        }
        .left3 img {
            height: 20em;
        }
        .middle3 {
            font-size: 30px;
        }
    }
</style>
