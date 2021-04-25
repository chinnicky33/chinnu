<template>
    <div class="video">

        <!-- Header -->
        <el-row>
            <el-col :xs="2" :sm="2" :md="2" :lg="2" :xl="2">
                <el-button @click="goBack()" class="back_button" type="danger" circle
                           icon="el-icon-d-arrow-left"></el-button>
            </el-col>
            <el-col :xs="24" :sm="24" :md="24" :lg="24" :xl="24">
                <h1 style="text-align:center">Video</h1>
            </el-col>
        </el-row>
 <div class="music-player">
            <audio
            
            :src="song"
            preload
            loop
           
            ></audio>
            <div  class="toggle-sound"></div>
       </div>
        <!-- Content -->
        <el-row type="flex" justify="center">
            <el-col :xs="50" :sm="10" :md="100" :lg="100" :xl="100">
            <div class="block" style="overflow:auto;margin-bottom:10vh" >

            <video :src="vid1"  :width="502" :height="260" id="video-container" controls></video>
             
            </div>

            <div class="block" style="overflow:auto;margin-bottom:10vh" >

            <video :src="vid2"  :width="502" :height="260" id="video-container" controls></video>
             
            </div>
             <div class="block" style="overflow:auto;margin-bottom:15vh" >

            <video :src="vid3"  :width="502" :height="260" id="video-container" controls></video>
             
            </div>
            <div class="block" style="overflow:auto;margin-bottom:15vh" >

            <video :src="vid4"  :width="502" :height="260" id="video-container" controls></video>
             
            </div>
            
            </el-col>
        </el-row>

         
    </div>
</template>

<script>

import vid1 from '../assets/vid1.mp4'
import vid2 from '../assets/vid2.mp4'
import vid3 from '../assets/vid3.mp4'
import vid4 from '../assets/vid4.mp4'
import song from '../assets/song.mp3'
    export default {
        name: "Video",
        data(){
            return {
                 vidshowTimeline: false,
                // TODO : Change the videoID to your youtube video's id
                // BTW, this is a Sam Smith song :)
                videoId : 'HSCymCubvhk',
                vid1:vid1,
                vid2:vid2,
                vid3:vid3,
                vid4:vid4,
                song:song
            }
        },
        methods: {
            goBack() {
                this.$router.go(-1);
            }
        }
    }
</script>

<style scoped>
    .back_button {
        margin-top: 15px;
        position:inherit;
        
    }
</style>