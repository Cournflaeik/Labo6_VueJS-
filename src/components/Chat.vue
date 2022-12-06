<script setup>

</script>

<template>
  <div class="chat">
    <h2>Comments</h2>
    <div class="comments">
      <h3 class="comment__username">

      </h3>
      <p class="comment__text">

      </p>
    </div>
    <div class="comments__add">
      <input type="text" v-model="comment" placeholder="Add a comment...">
      <button @click="addComment">Post</button>
    </div>
  </div>
</template>

<style scoped>

</style>
