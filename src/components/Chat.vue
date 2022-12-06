<script setup>
let comments = reactive({ comments: []})
let comment = ref('')

const addComment = () => {
  comments.comments.push({
    username: 'Elien',
    text: comment.value
  })
  fetch("https://lab5-p379.onrender.com/api/v1/messages/", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      username: "Elien",
      text: comment.value,
    }),
  })
  comment.value = ''
}
</script>

<template>
  <div class="chat">
    <h2>Comments</h2>
    <div v-for="comment in comments.comments" :key="comment.id" class="comments">
      <h3 class="comment__username">
        {{ comment.user }}
      </h3>
      <p class="comment__text">
        {{ comment.text }}
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
