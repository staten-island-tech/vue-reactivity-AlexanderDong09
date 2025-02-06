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
  width: 25%;
  border: solid;
  border-radius: 30px;
  border-color: var(--secondary);
  margin: 4rem;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease-in-out;
}

.astronomy-card img {
  max-width: 100%;
  transition: all 0.3s ease-in-out;
  border-radius: 10px;
  object-fit: contain;
  margin: 10px;
}

.astronomy-card img :hover {
  transform: scale(1.5); /* Scale up the card by 5% when hovered */
}
</style>
