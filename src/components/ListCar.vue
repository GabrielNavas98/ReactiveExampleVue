<template>
  <div class="car-list-container">
    <h1>Nuestros autos</h1>
    <div>
      <ul class="car-list">
        <li v-for="(car, index) in cars" :key="index">
          {{ car.branch + ' ' + car.model + ' '
          }}<button @click="$emit('deleteEvent', index)">X</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Car {
  branch: string
  model: string
}
defineProps<{ cars: Car[] }>()
</script>

<style scoped>
.car-list-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 8px;
  background-color: #f9f9f9;
}

h1 {
  text-align: center;
  color: #333;
}

.car-list {
  list-style-type: none;
  padding: 0;
}

.car-list li {
  padding: 0.5rem;
  border-bottom: 1px solid #ccc;
  color: #555;
}

.car-list li:last-child {
  border-bottom: none;
}
</style>
