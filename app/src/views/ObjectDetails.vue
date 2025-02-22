<template>
  <div>
    <div v-if="objectDetails" class="astronomy-card">
      <div class="title-container">
        <h1 class="text-7xl text-center">{{ objectDetails.name }}</h1>
        <FavoriteButton :astronomyObject="objectDetails" />
      </div>

      <img :src="objectDetails.imageURL" :alt="objectDetails.name" class="size-2/3" />
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
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.astronomy-card {
  width: 80%;
  border: solid;
  border-radius: 30px;
  border-color: var(--secondary);
  margin: 2rem;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease-in-out;
  background-color: rgba(2, 37, 26, 0.644);
}

.title-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 20px;
  height: auto;
}
</style>
