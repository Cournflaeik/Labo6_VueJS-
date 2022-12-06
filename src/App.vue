<script setup>
import VideoPlayer from './components/VideoPlayer.vue'
import VideoDetails from './components/VideoDetails.vue'
import Chat from './components/Chat.vue'

</script>

<template>
  <div>
    <h1>
      <img src="https://static.vecteezy.com/system/resources/previews/006/693/634/original/tik-tok-flat-icon-template-black-color-editable-tik-tok-flat-icon-symbol-flat-illustration-for-graphic-and-web-design-free-vector.jpg" alt="">
      Tiktok Clone
    </h1>
    <div class="app">
      <VideoPlayer />
      <VideoDetails />
    </div>
  </div>
</template>

<style scoped>
  img {
    width: 3rem;
    height: 3rem;
  }

  h1 {
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 1rem 0;
  }

  .app {
    display: grid;
    grid-template-columns: 8fr 4fr;
  }

</style>
