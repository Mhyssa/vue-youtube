<template>
    <div class="px-8 flex flex-col items-center">
        <div class="video-container sm:w-2/3 w-4/5">
            <iframe :src="`https://youtube.com/embed/${$route.params.id}`" 
            frameborder="0"
            class="video rounded-xl shadow-lg"></iframe>
        </div>
        <h3 class="mt-4 text-center text-lg">{{ videoInfo.title }}</h3>
    </div>
</template>

<style>

.video-container {
    padding-top: 40%;
    position: relative;
    margin: 0 auto 10px auto;
}

.video {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
}
</style>

<script>
    export default {
        name : "VideoDetails",
        data(){
            return {
                videoInfo : [],
            };
        },
        mounted(){
            const url = 'https://youtube138.p.rapidapi.com/video/details/?id='+this.$route.params.id;
            const options = {
                method: 'GET',
                headers: {
                    'X-RapidAPI-Key': 'c89b224b64msh55e4e7b77b36e21p1d6dc1jsnb7efb4d05201',
                    'X-RapidAPI-Host': 'youtube138.p.rapidapi.com'
	}
};
        fetch(url, options)
        .then(response => response.json())
        .then(data => this.videoInfo = data)
        .catch(error => console.error("c une erreur", error));
        },
        
};

</script>


