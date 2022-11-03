<script>
    import Player from "./Components/Player.svelte";
    import Header from "./Components/Header.svelte";
    import Footer from "./Components/Footer.svelte";
    import Social from "./Components/Social.svelte";
</script>

<style>
    :global(html){
        overflow-x: hidden;
        background-color: black;
        margin: 0 0 0 0; 
    }
    :global(body){
        overflow-x: hidden;
        position: relative;
        animation: mymove 10s infinite;
        padding: 0 0 0 0;
    }
    :global(*){
        margin: 0 0 0 0; 
        padding: 0; 
        border: 0; 
    }
    @keyframes mymove {
    0%   {background-color: rgba(231, 37, 137, 0.15);}
    25%  {background-color: rgba(62, 54, 238, 0.15);}
    50%  {background-color: rgba(54, 238, 230, 0.15);}
    75%  {background-color: rgba(238, 235, 54, 0.15);}
    100% {background-color: rgba(238, 70, 54, 0.15);}
}

</style>

<svelte:head>
    <meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1.0" />
    <meta name="apple-mobile-web-app-capable" content="yes" />
    <title>360 Radio Chile</title>
    <link rel="icon" type="image/jpg" href="/images/icon.jpg">
</svelte:head>

<Header/>
<Player/>
<Social/>
<Footer/>
<footer style="display: flex; justify-content:center; color: grey; flex-direction: row; text-align:center;">
    <a href="mailto: ventas@360radiochile.cl" style="text-decoration:none">
        Contacto Ventas
        <p><b>ventas@360radiochile.cl</b></p>
    </a>
</footer>