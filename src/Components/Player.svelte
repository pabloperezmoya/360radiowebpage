<script>
    window.onload = () => {
    const myAudio = document.getElementById('my-audio');
    const myControl = document.querySelector('.my-control');
    const slicer = document.querySelector('#slicer')
    const mute = document.querySelector('#mute')
    const input = document.querySelector('#playpause')
    let previus_data = null;
    
    function switchState() {
        if (myAudio.paused) {
        myAudio.play();

        
        } else {
        myAudio.pause();
        
        }
    }
    // myControl.addEventListener('click', () => {
    //     switchState();
    // }, false);
    
    input.addEventListener('click', () => {
        switchState();
    }, false);

    slicer.addEventListener('input', () =>{
        // console.log(slicer.value)

        // Linear
        // const volumeLog = slicer.value / 100 // Linear
        // myAudio.volume = volumeLog
        
        // Logaritmic
        const volumeLog = ( Math.log2(1+(slicer.value/100)) ).toFixed(2) // Log
        myAudio.volume = volumeLog
        
        // console.log(volumeLog)
    })
    // mute.addEventListener('click', () => {
    //     console.log(previus_data)
    //     if (previus_data != null & slicer.value == 0){
            
    //         slicer.value = previus_data
    //         myAudio.volume = ( Math.log2(1+(previus_data/100)) ).toFixed(2)
    //         previus_data = null
    //     }
    //     else{
    //         previus_data = slicer.value
    //         slicer.value = 0
    //         myAudio.volume = 0
    //     }
    // })
}
</script>

<audio
    id="my-audio"
    src="https://sonic-us.streaming-chile.com/8036/stream"
/>


<!-- <button class="my-control">play</button> -->
<main>
    <div class="playpause">
        <input type="checkbox" value="None" id="playpause" name="check" checked/>
        <label for="playpause"></label>
    </div>
    <!-- <button id="mute">mute</button> -->
    <input id="slicer" type="range" min=0 max=100>
</main>


<style>
main{
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
}
.playpause{
    margin-top: 2rem;
    margin-bottom: 2rem;
    border-radius: 60px;
    padding: 1rem 2rem 1rem 2rem;
    background-color: white;
    box-shadow: 2.7px 3.5px #888888;
}
.playpause > label {
    display: block;
    box-sizing: border-box;
    width: 0px;
    height: 74px;
    border-color: transparent transparent transparent rgb(0, 0, 0, 0.8);
    transition: 100ms all ease;
    cursor: pointer;
    border-style: double;
    border-width: 0px 0 0px 60px;
    padding: 0 0 0 -10px ;
}
.playpause > label:hover{
    border-color: transparent transparent transparent #8A8A8A;
}

.playpause > input[type="checkbox"] {
    position: absolute;
    left: -9999px;
}
.playpause > input[type="checkbox"]:checked + label {
    border-style: solid;
    border-width: 37px 0 37px 60px;
}

input[type=range] {
  height: 34px;
  -webkit-appearance: none;
  margin: 10px 0;

  width: 10rem;
  background-color: rgba(0,0,0,0);
  border-color: rgba(0,0,0,0);
}
input[type=range]:focus {
  outline: none;
}
input[type=range]::-webkit-slider-runnable-track {
  width: 100%;
  height: 14px;
  cursor: pointer;
  animate: 0.2s;
  box-shadow: 2px 2px 3px #A1A1A1;
  background: #FFFFFF;
  border-radius: 23px;
  border: 0px solid #8A8A8A;
}
input[type=range]::-webkit-slider-thumb {
  box-shadow: 2px 2px 2px #C4C4C4;
  box-shadow: 2px 2px 10px #888888;
  border: 0px solid #FAFAFA;
  height: 26px;
  width: 26px;
  border-radius: 25px;
  background: #FFFFFF;
  cursor: pointer;
  -webkit-appearance: none;
  margin-top: -6px;
}
input[type=range]::-webkit-slider-thumb:hover,input[type=range]::-webkit-slider-thumb:active {
    background: #8A8A8A;
}
input[type=range]:focus::-webkit-slider-runnable-track {
  background: #FFFFFF;
}
input[type=range]::-moz-range-track {
  width: 100%;
  height: 14px;
  cursor: pointer;
  animate: 0.2s;
  box-shadow: 2px 2px 3px #A1A1A1;
  background: #FFFFFF;
  border-radius: 23px;
  border: 0px solid #8A8A8A;
}
input[type=range]::-moz-range-thumb {
  box-shadow: 2px 2px 2px #C4C4C4;
  border: 0px solid #FAFAFA;
  height: 26px;
  width: 26px;
  border-radius: 25px;
  background: #FFFFFF;
  cursor: pointer;
}
input[type=range]::-ms-track {
  width: 100%;
  height: 14px;
  cursor: pointer;
  animate: 0.2s;
  background: transparent;
  border-color: transparent;
  color: transparent;
}
input[type=range]::-ms-fill-lower {
  background: #FFFFFF;
  border: 0px solid #8A8A8A;
  border-radius: 46px;
  box-shadow: 2px 2px 3px #A1A1A1;
}
input[type=range]::-ms-fill-upper {
  background: #FFFFFF;
  border: 0px solid #8A8A8A;
  border-radius: 46px;
  box-shadow: 2px 2px 3px #A1A1A1;
}
input[type=range]::-ms-thumb {
  margin-top: 1px;
  box-shadow: 2px 2px 2px #C4C4C4;
  border: 0px solid #FAFAFA;
  height: 26px;
  width: 26px;
  border-radius: 25px;
  background: #FFFFFF;
  cursor: pointer;
}
input[type=range]:focus::-ms-fill-lower {
  background: #FFFFFF;
}
input[type=range]:focus::-ms-fill-upper {
  background: #FFFFFF;
}
/* :global(body){
        background-color: black;
        color: white;
        animation: 1s infinite alternate ease-out breathing-color--dark;
    }

    @keyframes breathing-color--dark {
        from
        {
            background-color: black;
        }
        to
        {
            background-color: hsl(0, 0%, 7%);
        }
    } */

</style>