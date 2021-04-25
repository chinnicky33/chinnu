<template>
    <div class="landing" >
       
       
        <div class="heading">
          <button  class="heading" @click="playSound(song)"><h1>Start with Music</h1></button>
           <button  class="heading" @click="startwithout()"><h1>Start without Music</h1></button>
        </div>
    </div>

</template>

<script>

    import song from '../assets/song.mp3'

    export default {
        name: 'FirstPage',
        data() {
            // TODO : Change these messages to your own words ...
            
            return {
                isplaying:false,
                song:song,
                isfirst:true,
            }

        },
        mounted: function () {
            // console.log('Play outside of');
            // var audio = new Audio(require('../assets/song.mp3')); // path to file
            // audio.play();
            // console.log('Play outside of',audio);
            // console.log('Play outside of',audio.play());
        },
          methods: {
                playSound (sound) {
                
                if(!this.isplaying ) {
                    if (this.isfirst){
                    this.song = new Audio(sound);
                    this.isfirst=false
                    }
                    this.song.play();
                    this.isplaying=true;
                    this.$root.song=this.song
                    console.log("audioooo",this.isplaying,this.$root.song);
                    this.startwithout();
                } else {
                     this.song.pause()
                     this.isplaying=false;
                     console.log("audioooo11111",this.isplaying,this.song);
                     }
                },
                startwithout(){
                    this.$router.push('/home');
                }
            }
    }

</script>

<style scoped>
    .landing {
        line-height: 80vh;
        font-size: 1vw;
        color: beige;
    }
body {
  background-color: #5c4084;
  padding: 50px;
}

.container {
  padding: 40px 80px 15px 80px;
  background-color: #fff;
  border-radius: 8px;
  max-width: 400px;
}

.heading {
  text-align: center;
}
.heading h1 {
  background: -webkit-linear-gradient(#fff, #999);
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
  text-align: center;
  margin: 0 0 5px 0;
  font-weight: 900;
  font-size: 4rem;
  color: #fff;
}
.heading h4 {
  color: #a990cc;
  text-align: center;
  margin: 0 0 35px 0;
  font-weight: 400;
  font-size: 24px;
}

.btn {
  outline: none !important;
}



</style>

