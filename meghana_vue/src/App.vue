<template>
  <MusicHeader />
  <MusicList :musicList = musicList />
</template>

<script>
import  MusicHeader from "./components/MusicHeader.vue";
import MusicList from "./components/MusicList.vue";

 export default{
   name:"App",
   components:{
    MusicHeader,
    MusicList
   },
   data(){
    return{
      musicList:[]
    }
   },
   methods:{
    async displayMusicList(){
      const response = await fetch("http://localhost:3167/api");
      const musicData = await response.json();
      return musicData[0].songs;
    }
   },
   async created(){
    this.musicList = await this.displayMusicList();
   }
 }
</script>

<style>
  body{
        font-family: "Alegreya", serif;
    }
</style>