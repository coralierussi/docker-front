<script setup lang="ts">
import { ref, onMounted } from 'vue';

const message = ref('Chargement en cours...');
onMounted(async () => {

  const URL = 'https://docker-back-6ysl.onrender.com/toto'
  const response = await fetch(URL);
  if (!response.ok) {
    console.error('Error fetching data:', response.statusText);
    return;
  } else {
    const data = await response.json();
    message.value = data.message;
  }
  
});
</script>

<template>
  <div>
      
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
