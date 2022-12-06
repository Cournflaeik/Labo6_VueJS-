<script setup>
    import { onMounted, reactive, ref } from 'vue'
    import 'animate.css'
    let videos = reactive({data: []})
    let videoSrc = ref("")
    let animation = ref("")
    let counter = ref(0)
    
    onMounted(() => {
        const apiUrl = 'https://app.fakejson.com/q/aEP7kjZO?token=BK-zS3RgLrj-gU5pP2v1Dw'
        // fetch
        fetch(apiUrl)
            .then(res => res.json())
            .then(data => {
                videos.data = data.videos
                videoSrc.value = (data.videos[0].video)
            })
    })

    const nextVideo = () => {
        animation.value = "animate__fadeOut"
        counter.value ++
        setTimeout(() => {
        videoSrc.value = videos.data[counter.value].video
        animation.value = "animate__fadeIn"
        }, 1000)
    }

    const previousVideo = () => {
        animation.value = "animate__fadeOut"
        counter.value --
        setTimeout(() => {
        videoSrc.value = videos.data[counter.value].video
        animation.value = "animate__fadeIn"
        }, 1000)
    }

</script>

<template>
  <div class="blur">
    <div class="controlls">
        <a @click.prevent="previousVideo" href="#">⬆</a>
        <a @click.prevent="nextVideo" href="#">⬇</a>
    </div>
    <video 
        :src="videoSrc"
        :class="animation"
        class="animate__animated"
        autoplay
        muted
        loop
    ></video>
  </div>
</template>

<style scoped>
    video{
        max-width: 100%;
        max-height: 100vh;
    }

    .blur {
        background-image: url(ss.jpg);
        background-size: cover;
        text-align: center;
        position: relative;

    }

    .controlls {
        position: absolute;
        top: 40%;
        right: 1rem;
        display: flex;
        flex-direction: column;
        color: rgb(0, 0, 0);
        background-color: aliceblue;
        border-radius: .5rem;
    }

    a {
        font-size: 2rem;
        text-decoration: none;
        padding: .8rem;
    }
</style>
