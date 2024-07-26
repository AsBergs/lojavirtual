<script setup>
import { ref } from 'vue';
import { onBeforeRouteUpdate } from 'vue-router';

const showMenu = ref(false);

onBeforeRouteUpdate(() => {
  showMenu.value = false;
});
</script>
<template>
  <div id="footerMenu" :style="{ display: showMenu ? 'block' : 'none' }">
    <RouterLink to="/">
      <i class="mdi mdi-home-outline" />
      Home
    </RouterLink>
    <RouterLink to="/login">
      <i class="mdi mdi-account" />
      Login
    </RouterLink>
  </div>
  <div class="icons">
    <RouterLink to="/acessorios" class="icon-link">
      <i class="icon mdi mdi-tire" />
    </RouterLink>
    <RouterLink to="/categorias" class="icon-link">
      <i class="mdi mdi-car-convertible" />
    </RouterLink>
    <RouterLink to="/cores" class="icon-link">
      <i class="icon mdi mdi-palette" />
    </RouterLink>
    <RouterLink to="/marcas" class="icon-link">
      <i class="icon mdi mdi-watermark" />
    </RouterLink>
    <RouterLink to="/modelos" class="icon-link">
      <i class="icon mdi mdi-van-passenger" />
    </RouterLink>
    <RouterLink to="/veiculos" class="icon-link">
      <i class="icon mdi mdi-car-back" />
    </RouterLink>

    <div class="hamburger" @click="showMenu = !showMenu">
      <i class="mdi mdi-menu" />
    </div>
  </div>
</template>


<style scoped>
#footerMenu {
  position: fixed;
  bottom: 15%;
  right: 0;

  width: 20%;
  border-top: #eeeeee 1px solid;
  background-color: white;

  display: block;
  padding: 1rem;
}

#footerMenu a {
  display: flex;
  width: 100%;
  justify-content: space-between;
  text-decoration: none;
  color: #282828;
  font-size: 1rem;
  transition: color 0.3s;
}

.icons {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: space-between;
  font-size: 1.7rem;
}

.icons a {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #282828;
  font-size: 1rem;
  transition: color 0.3s;
}

.hamburger:hover {
  cursor: pointer;
}
</style>
