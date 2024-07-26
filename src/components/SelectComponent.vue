<script setup>
defineProps(['label', 'list'])
</script>
<template>
  <select  name="cores" id="cores">
    <option value="" disabled selected>{{ label }}</option>
    <option :value="i.id" v-for="i in list" :key="i.id">
      {{ i?.nome? i?.nome: i?.descricao }}
    </option>
  </select>
</template>
<style scoped>

  select {
  border-radius: 5px;
  width: 100%; 
  padding: 0.8vw; 
  border: solid #797e8c 1px; 
  box-sizing: border-box; 
  font-size: 1rem; 
}

select:invalid {
  color: gray; 
}


@media (max-width: 1200px) {
  select {
    width: calc(100% - 2vw); 
    font-size: 0.9rem; 
  }
}

@media (max-width: 768px) {
  select {
    width: calc(100% - 2vw); 
    font-size: 0.8rem; 
  }
}

@media (max-width: 480px) {
  select {
    width: calc(100% - 3vw);
    font-size: 0.8rem; 
    padding: 1vw;
  }
}

</style>
