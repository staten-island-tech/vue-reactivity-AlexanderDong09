<template>
  <div>
    <button
      class="bg-blue-500 p-2 rounded text-center cursor-pointer transition-all hover:scale-105 active:scale-95"
      @click="toggleFavorite"
    >
      {{ data ? 'Unfavorite' : 'Favorite' }}
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { defineEmits } from 'vue'

const obj = defineProps({
  object: Object,
})

const data = ref(obj.object.isFavorited)
const eventEmitters = defineEmits(['toggleFavoriter'])

function toggleFavorite() {
  eventEmitters('toggleFavoriter')
  data.value = !data.value
}
</script>

<style scoped></style>
