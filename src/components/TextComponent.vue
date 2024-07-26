<script setup>
defineProps(["label"]);
const model = defineModel();
</script>
<template>
  <span class="input-container">
    <input type="text" :placeholder="label" v-model="model" />
  </span>
</template>
<style scoped>

input {
  padding: 0.8vw;
  border-radius: 5px;
  border: solid #797e8c 1px;
  outline: none;
  width: 100%;
  box-sizing: border-box; 
  font-size: 1rem; 
}

@media (max-width: 1200px) {
  input {
    padding: 0.8vw; 
    width: calc(100% - 2vw);
    font-size: 0.9rem; 
  }
}

@media (max-width: 768px) {
  input {
    padding: 1vw; 
    width: calc(100% - 2vw); 
    font-size: 0.8rem; 
  }
}

@media (max-width: 480px) {
  input {
    padding: 1.2vw; 
    width: calc(100% - 3vw); 
    font-size: 0.8rem;
  }
}

</style>