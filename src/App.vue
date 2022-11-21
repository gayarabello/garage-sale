<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div
    style="display: flex; justify-content: space-between; align-items: center"
  >
    <h1>Loja da Alegria</h1>
    <div>
      <RouterLink style="margin-right: 1rem" to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </div>
  </div>
  <RouterView />
</template>

<style scoped>
/* @media (min-width: 1024px) {

} */
</style>
