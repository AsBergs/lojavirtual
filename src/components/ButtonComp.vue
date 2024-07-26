<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(['salvar, limpar']);
</script>

<template>
  <button @click="$emit('salvar')">Salvar</button>
  <button @click="$emit('limpar')">Limpar</button>
</template>
 

