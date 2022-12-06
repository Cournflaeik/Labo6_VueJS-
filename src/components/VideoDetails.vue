<script setup>
    import { onMounted, ref } from 'vue'
    
    let username = ref("")
    let description = ref("")

    onMounted(() => {
        const apiUrl = 'https://app.fakejson.com/q/aEP7kjZO?token=BK-zS3RgLrj-gU5pP2v1Dw'
        // fetch
        fetch(apiUrl)
            .then(res => res.json())
            .then(data => {
                username.value = (data.videos[0].username)
                description.value = (data.videos[0].description)
            })
    })

</script>

<template>
  <div class="details">
    <h3>{{username}}</h3>
    <p>{{description}}</p>
  </div>
</template>

<style scoped>
  .details {
    padding: 1rem;
  }
</style>
