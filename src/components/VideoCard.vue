<template>
    <router-link :to="`video/${videoInfo.video.videoId}`">
        <div
        class=" w-40 h-44 m-2 p-2 rounded-xl bg-white shadow-lg"
        @mouseover="isHovering = true"
        @mouseleave="isHovering = false"
        >
        <img 
        :src="isHovering  &&
            videoInfo.video.movingThumbnails  &&
            videoInfo.video.movingThumbnails.length > 0
            ? videoInfo.video.movingThumbnails[0].url 
            : videoInfo.video.thumbnails[0].url
            " 
            alt="thumbnails"
            class="rounded-t-xl mb-2">
            <h3 class="font-bold line-clamp-2 text-sm">{{ videoInfo.video.title }}</h3>
            
            <!-- <span>{{ videoInfo.video.lengthSeconds }} seconds</span> -->
            <p class="text-xs">{{ videoInfo.video.stats.views }} views - {{ videoInfo.video.publishedTimeText }}</p>
        </div>
    </router-link>
</template>

<script>
    export default{
        name: "VideoCard",
        props: {
            videoInfo: Object,
        },
        data() {
            return {
                isHovering: false,
            };
        },
    };
</script>
