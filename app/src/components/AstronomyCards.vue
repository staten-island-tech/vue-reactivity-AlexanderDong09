<template>
  <div class="astronomy-card">
    <h1>{{ name }}</h1>
    <img :src="imageURL" :alt="altText" />
  </div>
</template>

<script setup>
defineProps({
  name: String,
  imageURL: String,
  altText: String,
})
</script>

<style scoped>
.astronomy-card {
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 20px;
  margin: 10px;
  text-align: center;
  width: 200px;
}

.astronomy-card img {
  max-width: 100%;
  border-radius: 8px;
}
</style>
