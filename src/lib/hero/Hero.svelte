<script lang="ts">
    import ghost1 from "../../assets/ghost1.svg";
    import happy from "../../assets/happy.svg";
    import annoyed from "../../assets/annoyed.svg";
    import wtfh from "../../assets/wtfh.svg";
    import question from "../../assets/question.svg";
    import exclaim from "../../assets/exclaim.svg";
    import filler1 from "../../assets/filler1.svg";
    import filler3 from "../../assets/filler3.svg";
   const listitems = [
        {image:filler1,top:'20em',right:'-50em',bottom:'0em',left:'0em'},
        {image:filler3,top:'-34em',right:'0em',bottom:'0em',left:'-40em'},
    ]
    let value = 1;
    setInterval(() => {
        value = -value;
    }, 1000);
</script>

<section class="container1" >
    {#each listitems as item}
    <div class="filler" style="margin:{item.top} {item.right} {item.bottom} {item.left}">
        <img src={item.image} alt="" />
    </div>
    {/each}
    
    <div class="left1">
        <img src={ghost1} class="img" alt="ghost" />
    </div>
    <div class="right1">
        <span class="greeting">Hello !</span>
        <span class="greeting2">I'm Syam SV</span>
    </div>
</section>
<section class="container2" id="about">
    <div class="left2">
        Coding is a huge source of inspiration for me. I enjoy doing it and
        providing memorable experiences for others. I usually sleep or listen to
        music when I'm not coding or discovering new things.
    </div>
    <div class="right2">
        <div>
            <img src={happy} alt="" class="img2" />
        </div>
        <div>
            <img
                src={annoyed}
                alt=""
                class="img2"
                style="transform:scaleX({value})"
            />
            <img src={value == 1 ? question : exclaim} alt="" class="img3" />
        </div>
        <div>
            <img src={wtfh} alt="" class="img2" />
        </div>
    </div>
</section>

<style>
    .filler{
        position:absolute;
    }
    .filler img{
        width:100%;
        height:100%;
    }
    .img {
        height: 30em;
        padding: 1.5em;
        will-change: filter;
        pointer-events: none;
    }
    .img2 {
        height: 20em;
        padding: 1.5em;
        will-change: filter;
        pointer-events: none;
    }
    .img3 {
        height: 6em;
        position: absolute;
        transform: rotate(15deg);
        margin-top: -2em;
        margin-left: -5em;
    }

    .container1 {
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        height:100vh;
    }
    .container2 {
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        padding: 0 10rem;
    }
    .left2 {
        font-size: 30px;
        text-align: justify;
    }
    .right2 {
        display: flex;
        flex-direction: row;
        text-align: justify;
    }
    .right1 {
        display: flex;
        flex-direction: column;
    }
    .greeting {
        font-size: 7em;
    }
    .greeting2 {
        font-size: 4em;
    }
    @media screen and (max-width: 1500px){
        .container2{
            flex-direction: column;
        }
        .right2{
            padding-top: 3em;
        }
        .filler{
            display: none;
        }
    }
    @media screen and (max-width: 1100px) {
        .container1 {
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }
        .container2 {
            flex-direction: column;
            align-items: center;
            padding: 0 3em;
        }
        .img2 {
            height: 10em;
        }
        .img3 {
            height: 3em;
            margin-top: 1em;
            margin-left: -2em;
        }
        .left2{
            text-align: center;
        }

        .right1 {
            align-items: center;
        }
        .greeting {
            font-size: 6em;
        }
        .greeting2 {
            font-size: 3em;
        }
    }
</style>
