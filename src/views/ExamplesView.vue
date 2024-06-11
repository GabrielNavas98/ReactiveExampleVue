<script setup lang="ts">
import AddCar from '@/components/AddCar.vue'
</script>

<template>
  <div class="examples">
    <h1>This is an examples page</h1>
    <AddCar />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .examples {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
