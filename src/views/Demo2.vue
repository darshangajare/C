<template>
<div>
    
    <h1 id="head">hiii</h1>
    <div id="btn">
    <button @click=" hellofun">Click</button>
    </div>
    <device type="media" onchange="update(this.data)">Video</device>
    <video autoplay></video>
    </div>
</template>
<script>
// import { url } from 'inspector'

// function printmsg(){
//     document.getElementById("txt").innerHTML="add successfull";
//     }
    // function start(){
    // window.setTimeout(printmsg,50);
    // }

export default {
    name: 'Demo2',
    data(){

    },
    methods:{
        hellofun(){
            document.getElementById("head").innerHTML="Darshan";
             if (this.hasGetUserMedia()) {
        // alert("Available")
         navigator.getUserMedia({video: true, audio: true}, function(localMediaStream) {
        var video = document.querySelector('video');
        video.src = window.URL.createObjectURL(localMediaStream);})
        } else {
        alert('getUserMedia() is not supported in your browser');
        }
    },
    hasGetUserMedia() {
    return !!(navigator.getUserMedia || navigator.webkitGetUserMedia ||
            navigator.mozGetUserMedia || navigator.msGetUserMedia);
    // }

        // if (hasGetUserMedia(true)) {
         // Good to go!
        // } else {
        // alert('getUserMedia() is not supported in your browser');

    },
    update(stream) {
            document.querySelector('video').src = stream.url;
    } 
    }
}
</script>





<style>
#btn{
    border: 5px solid black;
}
</style>
