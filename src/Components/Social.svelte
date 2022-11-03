<script>
    let imagesPath = "/images/"
    let twitterIcon = imagesPath + "Twitter-icon.png"
    let instagramIcon = imagesPath + "Instagram-icon.png"
    let facebookIcon = imagesPath + "Facebook-icon.png"
</script>

<div class="imgscontainer">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="images">
        <img class="image facebook" src="{facebookIcon}" alt="Facebook" on:click={() => window.open("https://www.facebook.com/360radiodechile")}>
        <img class="image instagram" src="{instagramIcon}" alt="Instagram" on:click={() => window.open("https://www.instagram.com/360radiochile/")}>
        <img class="image twitter" src="{twitterIcon}" alt="Twitter" on:click={() => window.open("https://twitter.com/360radiochile")}>
    </div>
</div>

<style>
    .images{
        display: flex;
        height: 2.5rem;
        justify-content: center;
        margin-top: 2rem;
    }
    .image{
        margin-right: 1rem;
        margin-left: 1rem;
        border-radius: 50%;
    }
    .image:hover{
        background-color: #8A8A8A;
        cursor: pointer;
    }
</style>