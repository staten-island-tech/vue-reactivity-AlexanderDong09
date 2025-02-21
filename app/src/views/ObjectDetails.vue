<template>
  <div>
    <div v-if="objectDetails">
      <div class="title-container">
        <h1 class="text-7xl text-center">{{ objectDetails.name }}</h1>
        <FavoriteButton :astronomyObject="objectDetails" />
      </div>

      <img :src="objectDetails.imageURL" :alt="objectDetails.name" />
      <h3>Type of Object: {{ objectDetails.type }}</h3>
      <h4>
        Distance to Earth (in light-years): {{ objectDetails.distanceLightYears.toLocaleString() }}
      </h4>
      <h5>Discovery Year of Object: {{ objectDetails.discoveryYear }}</h5>
      <h6>{{ objectDetails.notableFeatures }}</h6>
    </div>
    <div v-else>
      <p>Object not found.</p>
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import { astronomyObjects } from '@/arrays/objects.js'
import FavoriteButton from '@/components/FavoriteButton.vue'

const route = useRoute()

const objectDetails = computed(() => {
  return astronomyObjects.find((obj) => obj.name === route.params.name)
})

// function handleToggleFavorite() {
//   objectDetails.value.isFavorited = !objectDetails.value.isFavorited
// }
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  justify-content: center; /* Center vertically */
  align-items: center; /* Center horizontally */
  text-align: center; /* Center text */
}

.title-container {
  display: flex;
  flex-direction: row;
  align-items: center; /* Aligns text and button at the top */
  justify-content: center; /* Centers them horizontally */
  gap: 20px; /* Space between the heading and button */
  height: auto; /* Ensures the container is only as tall as the content */
}
</style>
