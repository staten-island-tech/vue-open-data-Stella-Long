<script setup>
import { onMounted, ref } from 'vue'
const data = ref([])

onMounted(async () => {
  try {
    const response = await fetch('https://data.cityofnewyork.us/resource/kun8-kdsr.json')
    
    if (!response.ok) {
      
    }
    data.value = await response.json()
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <div v-for="item in data" :key="item.id">
    {{ item }}    
  </div>
</template>

<style scoped></style>
