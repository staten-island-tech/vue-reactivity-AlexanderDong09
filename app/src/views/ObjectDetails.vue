<template>
  <div>
    <div v-if="objectDetails">
      <h1 class="text-7xl text-center">{{ objectDetails.name }}</h1>
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

const route = useRoute()

const objectDetails = computed(() => {
  return astronomyObjects.find((obj) => obj.name === route.params.name)
})
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  justify-content: center; /* Center vertically */
  align-items: center; /* Center horizontally */
  min-height: 100vh; /* Make sure it takes at least the full height of the viewport */
  text-align: center; /* Center text */
}
</style>
