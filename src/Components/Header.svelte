<script>
    let imagePath = "/images/360radio2.gif"
    let videoPath = "/images/Video.webm"

    window.onload = async()=>{
        let videoElem = document.getElementById("video");
        await videoElem.play();
    }
</script>

<nav>
    
    <!-- <h1>360 Radio</h1> -->
    <!-- svelte-ignore a11y-media-has-caption -->
    <video loop autoplay src="{videoPath}"></video>
</nav>

<style>
    /* img{
        margin-top: 0.4rem;
        height: 5rem;
        
    } */
    nav{
        display: flex;
        justify-content: center;
        margin-bottom: 4rem;
        width: 80%;
        margin-left: auto;
        margin-right: auto;
        background-color: black;
        height: 6rem;
        border-radius: 0 0 2rem 2rem;
    }
    /* h1{
        font-size: 2.4rem;
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        text-shadow: 2px 2px 2px grey;
        color: white;
    } */
</style>