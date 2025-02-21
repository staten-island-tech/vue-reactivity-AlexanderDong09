<template>
  <div class="about">
    <h1 class="text-5xl font-bold underline pb-5">Favorite Items!</h1>
    <div v-if="favObjects.length > 0" class="card-container">
      <AstronomyCards
        v-for="object in favObjects"
        :key="object.name"
        :name="object.name"
        :imageURL="object.imageURL"
      ></AstronomyCards>
    </div>
    <h1 v-else>You have nothing favorited, go favorite something!</h1>
  </div>
</template>

<script setup>
import AstronomyCards from '@/components/AstronomyCards.vue'
import { astronomyObjects } from '@/arrays/objects.js'
import { favObjects } from '@/arrays/favObjects'

astronomyObjects.forEach((object) => {
  if (object.isFavorited === false) {
    console.log(object)
  }
})
</script>

<style scoped>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

h1 {
  text-align: center;
}
</style>
