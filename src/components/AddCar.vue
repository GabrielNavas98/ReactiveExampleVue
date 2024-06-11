<template>
  <div class="form-container">
    <h1>Agregar</h1>
    <div class="form-group">
      <label for="branch">Marca</label>
      <input
        v-model="newCar.branch"
        id="branch"
        type="text"
        placeholder="Ingresa la marca de un auto"
      />
    </div>
    <div class="form-group">
      <label for="model">Modelo</label>
      <input
        v-model="newCar.model"
        id="model"
        type="text"
        placeholder="Ingresa el modelo de un auto"
      />
    </div>
    <button type="submit" @click="handleAdd">Agregar</button>
  </div>
  <div>
    <ListCar :cars="cars" @delete-event="deleteCar" />
  </div>
</template>

<script setup lang="ts">
import ListCar from '@/components/ListCar.vue'
import { reactive } from 'vue'

const newCar = reactive({ branch: '', model: '' })
let cars = reactive([
  { branch: 'Toyota', model: 'Corolla' },
  { branch: 'Honda', model: 'Civic' },
  { branch: 'Ford', model: 'Mustang' },
  { branch: 'Chevrolet', model: 'Camaro' },
  { branch: 'Tesla', model: 'Model S' },
  { branch: 'BMW', model: 'X5' },
  { branch: 'Audi', model: 'A4' },
  { branch: 'Mercedes-Benz', model: 'C-Class' },
  { branch: 'Nissan', model: 'Altima' },
  { branch: 'Volkswagen', model: 'Golf' }
])

const handleAdd = () => {
  cars.push({ branch: newCar.branch, model: newCar.model })
}

const deleteCar = (index: number) => {
  cars.splice(index, 1)
}
</script>

<style scoped>
.form-container {
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

.form-group {
  margin-bottom: 1rem;
}

label {
  display: block;
  margin-bottom: 0.5rem;
  color: #555;
}

input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

button {
  display: block;
  width: 100%;
  padding: 0.75rem;
  border: none;
  border-radius: 4px;
  background-color: #007bff;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}
</style>
