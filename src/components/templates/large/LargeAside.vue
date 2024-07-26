<script setup>
import LogoTitle from '@/components/templates/LogoTitle.vue';
</script>
<template>
  <div class="logo_and_menu">
    <logo-title class="mb-2" />
    <div class="divider" />
    <div class="menu">
      <router-link to="/acessorios" class="menu-item">
         Acessório
      </router-link>
      <router-link to="/categorias" class="menu-item">
       Categoria
      </router-link>
      <router-link to="/cores" class="menu-item">
        Cor
      </router-link>
      <router-link to="/marcas" class="menu-item">
        Marca
      </router-link>
      <router-link to="/modelos" class="menu-item">
       Modelo
      </router-link>
      <router-link to="/veiculos" class="menu-item">
       Veículo
      </router-link>
      <router-link to="/login" class="menu-item">
        <i class="icon mdi mdi-account" /> Login
      </router-link>
    </div>
  </div>
</template>

<style scoped>
.mb-2 {
  margin-bottom: 1.5rem;
}

.icon {
  font-size: 2rem;
  align-self: center;
  transition: transform 0.3s ease;
}

.divider {
  margin-top: 1rem;
  border-top: 1px solid #eeeeee;
}

.menu {
  padding: 3rem;
  display: flex;
  flex-direction: column;
}

.menu-item {
  display: flex;
  align-items: center;
  text-decoration: none;
  color: #282828; 
  gap: 1rem;
  font-size: 1.3rem;
  margin-top: 1rem;
  padding: 0.1rem 1rem; 
  width: 100%;
  box-sizing: border-box;
  transition: background-color 0.3s ease, color 0.3s ease, transform 0.3s ease;
}

.menu-item:hover {
  background-color: #3333333f; 
  color: #ffffff; 
  transform: scale(1.02); 
}

.menu-item:hover .icon {
  transform: scale(1.1); 
}

.menu-item:active {
  background-color: #444444; 
}
</style>
