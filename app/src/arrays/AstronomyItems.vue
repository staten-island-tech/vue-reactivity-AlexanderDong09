<template>
  <div class="card-container">
    <!-- <h2 v-for="object in astronomyObjects" :key="object.name">{{ object.name }}</h2> -->
    <AstronomyCards
      v-for="object in astronomyObjects"
      :key="object.name"
      :name="object.name"
      :imageURL="object.imageURL"
    ></AstronomyCards>
  </div>
</template>

<script setup>
import AstronomyCards from '@/components/AstronomyCards.vue'

import { astronomyObjects } from '@/arrays/objects.js'
</script>

<style scoped>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>
