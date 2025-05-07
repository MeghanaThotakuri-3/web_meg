<template>
    <div class="music-card">
        <img :src=song.song_image alt = song.song_title />
        <div>
             <span :style="{backgroundColor: getRandomColor(song.song_id)}" class="badge text-size">
                {{song.album_name}}
            </span>
             <div class="music-flex">
                <img src="@/assets/music.gif" alt="Animated Title"  class="anim_icon"/>
                <h2>{{song.song_title}}</h2>
             </div>
             <div class="music-flex">
                <img src="@/assets/artist.gif" alt="Animated Artist"  class="anim_icon"/>
                <p class="artist-name">{{song.artist_name}} </p>
                <img src="@/assets/calendar.gif" alt="Animated Calendar"  class="anim_icon"/>
                <span :style="{border: '1px solid'+ getRandomColor(song.song_id),color: getRandomColor(song.song_id),fontWeight:'bold'}" class="badge">
                    {{song.release_year}}</span>
             </div>
            <span class="text-size">
                <i class="fa fa-step-backward"></i>&nbsp;
                {{song.genre}}
                <i class="fa fa-step-forward"></i>&nbsp;
            </span> 
            <div class="music-flex">
                <div class="progress" :style="{background: '-webkit-linear-gradient(left,'+getRandomColor(song.song_id)+' 32%, white 10%)'}"></div>
                <p>{{song.song_duration}}</p>
            </div>
        </div>
    </div>
</template>

<script>
 export default{
    name:"MusicCard",
    props:{
        song: Object
    },
    methods:{
        getRandomColor(index) {
            const colors = ['#ffd1dc', '#d1c4e9', '#c8e6c9', '#b2ebf2', '#ffe4b5', '#ffecb3', '#b2ebf2'];
            return colors[index-1];
        }
    }
 }
</script>

<style>
    .music-card{
        display: flex;
        align-items: center;
        gap:2em;
        border:transparent;
        border-radius: 4px;
        padding: 10px;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
        font-family: "Alegreya", serif;
    }

    .music-card img{
        width:200px;
        height:100%;
        object-fit:cover;
    }

    .badge{
        padding: 0.5em;
        border-radius:5px;
    }

    .artist-name img{
        width: 20px;
        height:20px;
        vertical-align: middle;
    }
    .music-flex{
        display:flex;
        align-items:center;
        gap: 0.5em;
        font-family: "Alegreya", serif;
        font-size: 18px;
    }

    .music-flex img{
        width: 20px;
        height:20px;
        vertical-align: middle;
    }

    .progress{
        width: 200px;
        height: 4px;
        border: 1px solid grey;
        border-radius: 2px;
        margin:auto;
    }

    .text-size{
        font-size: 18px;
    }
</style>