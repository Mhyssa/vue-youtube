<template>
    <div class="sm:px-32 flex flex-wrap justify-center">
        <VideoCard  v-for="video in videos" :key="video.id" :videoInfo="video"/>
    </div>
</template>

<script>
import VideoCard from "../components/VideoCard.vue";

    export default{
        name: "HomeFeed",
        components: {
            VideoCard,
        },
        data(){
            return {
                videos: [],
            };
        },
        mounted(){
            const url = 'https://youtube138.p.rapidapi.com/channel/videos/?id=UC8g5sJFyraYb4Xl_lRHW-Jg&filter=videos_latest';
            const options = {
            method: 'GET',
            headers: {
                'X-RapidAPI-Key': 'c89b224b64msh55e4e7b77b36e21p1d6dc1jsnb7efb4d05201',
                'X-RapidAPI-Host': 'youtube138.p.rapidapi.com'
            }
        };

        fetch(url, options).then(response=>response.json()).then(data => this.videos = data.contents).catch(error => console.log("Problem fetching", error)) 
        }
    };
    
</script>