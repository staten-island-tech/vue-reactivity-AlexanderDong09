<template>
  <div>
    <button class="cursor-pointer" @click="toggleFavorite">unfavor</button>

    <!--
        <button
      class="px-6 py-3 bg-blue-500 text-white rounded hover:bg-blue-600"
      @click="toggleFavorite"
    >
      Click Me
    </button>
    
    -->
  </div>
</template>

<script setup>
import { favObjects } from '@/arrays/favObjects'
import { ref, computed } from 'vue'

const obj = defineProps({
  object: Object,
})

function toggleFavorite() {}
</script>

<style scoped></style>
