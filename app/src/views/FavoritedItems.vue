<template>
  <div class="about">
    <h1 class="text-5xl font-bold underline pb-5">Favorite Items!</h1>
    <h1 v-if="!hasItems">You have nothing favorited, go favorite something!</h1>
  </div>
</template>

<script setup>
import favObjects from '@/arrays/FavoritedItems.vue'
</script>

<style></style>
