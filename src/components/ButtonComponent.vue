<script setup>
import { defineEmits } from 'vue';
const $emit = defineEmits(['salvar, limpar']);
</script>

<template>
  <button @click="$emit('salvar')">Salvar</button>
  <button @click="$emit('limpar')">Limpar</button>
</template>

<style scoped>
button {
  background-color: #000000;
  color: #fff;
  border: none;
  padding: 0.5rem 1rem; 
  border-radius: 25px; 
  font-size: 0.9rem; 
  cursor: pointer;
  transition: background-color 0.3s, color 0.3s;
}

button:hover {
  background-color: #333; 
}

.button-container {
  display: flex;
  gap: 0.5rem;
}

@media (max-width: 768px) {
  h1 {
    font-size: 1.5rem;
  }

  button, .btn-excluir {
    padding: 0.4rem 0.8rem;
    font-size: 0.8rem; 
  }}

  @media (max-width: 480px) {

  button, .btn-excluir {
    padding: 0.3rem 0.6rem; 
    font-size: 0.7rem; 
  }
  }


</style>