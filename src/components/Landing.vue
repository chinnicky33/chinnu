<template>
    <div class="landing" >
       
        <transition name="slide-fade">
            
            <h1 class="landing_text" :style="{ backgroundImage: `url(${coverImage})` }" v-if="show">{{message}} </h1>
        </transition>
    </div>
</template>

<script>
 import img1 from '../assets/1.jpeg'
  import img2 from '../assets/9.jpeg'
   import img3 from '../assets/10.jpeg'
    import img4 from '../assets/11.jpeg'
     import img5 from '../assets/12.jpeg'
      import img6 from '../assets/15.jpeg'
       import img7 from '../assets/16.jpeg'
        import img8 from '../assets/17.jpeg'
        import song from '../assets/song.mp3'

    export default {
        name: 'Landing',
        data() {
            // TODO : Change these messages to your own words ...
            let landingMessages = [
                "Welcome to My princess Jaanu's Birthday",
                "This is not a Big Surprise or Gift...",
                "But It's a Small try from me ...",
                "To make your Birthday more memorable...",
                "So, Lets quickly get into this...",
                "Here are Some Interesting things ....",
                "About you and your birthday.....",
                "Are you ready for the experience...?"
            ];
             let landingImages = [img1,img2,img3,img4,img5,img6,img7,img8];
             console.log("count1",this.count)
             
            return {
                message: "",
                messages: landingMessages,
                show: true,
                song:song,
                showButton: false,
                coverImages:landingImages,
                count: 0,
                maxCount: landingMessages.length - 1
            }

        },
        mounted: function () {
            console.log('Play outside of');
            var audio = new Audio(require('../assets/song.mp3')); // path to file
            audio.play();
            console.log('Play outside of',audio);
            console.log('Play outside of',audio.play());
            this.message = this.messages[this.count];
            this.coverImage = this.coverImages[this.count];
            setTimeout(this.fadeText, 2000);
        },
        methods: {
            fadeText() {
                this.show = false;
                this.count++;
                this.message = this.messages[this.count];
                this.coverImage = this.coverImages[this.count];
                setTimeout(this.showText, 1250);
            },
            showText() {
                this.show = true;
                if (this.count !== this.maxCount) {
                    setTimeout(this.fadeText, 2250);
                } else {
                    this.showButton = true;
                    setTimeout(() =>this.$router.push('/home'), 3000);
                }
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

    .landing_text {
        vertical-align: baseline;
        text-align: end;
    }

    .background_image{
       width: null;
       height: null;
    }
</style>
