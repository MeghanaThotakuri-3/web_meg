<template>
    <div class="grid-layout">
        <div v-for="song of musicList" :key="song.song_id">
            <MusicCard :song = song />
        </div>
    </div>
</template>

<script>
import MusicCard from "./MusicCard.vue";

 export default{
    name:"MusicList",
    components:{
        MusicCard
    },
    props:{
        musicList: Array
    }
 }
</script>

<style scoped>
    .grid-layout{
        display: grid;
        grid-template-columns: auto auto;
        gap: 2em;
    }
</style>