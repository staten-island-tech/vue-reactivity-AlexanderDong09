<template>
  <div>
    <button
      class="bg-blue-500 p-2 rounded text-center cursor-pointer transition-all hover:scale-105 active:scale-95"
      @click="toggleFavorite"
    >
      {{ isFavorited ? 'Unfavorite' : 'Favorite' }}
    </button>
  </div>
</template>

<script setup>
import { computed } from 'vue'
// import { defineEmits } from 'vue'

import { favObjects } from '@/arrays/favObjects.js'

const objProp = defineProps({
  astronomyObject: Object,
})

const isFavorited = computed(() => {
  return favObjects.some((obj) => obj.name === objProp.astronomyObject.name)
})

const toggleFavorite = () => {
  const index = favObjects.findIndex((obj) => obj.name === objProp.astronomyObject.name)

  if (index === -1) {
    favObjects.push({ ...objProp.astronomyObject })
  } else {
    favObjects.splice(index, 1)
  }

  console.log(favObjects)
}

// const toggleFavorite = () => {
//   if (!objProp.object) return

//   if (isFavorited === true)
// }

// const data = ref(objProp.object.isFavorited)
// const eventEmitters = defineEmits(['toggleFavoriter'])

// function toggleFavorite() {
//   eventEmitters('toggleFavoriter')
//   data.value = !data.value
// }
</script>

<style scoped></style>
