<script setup lang="ts">
import ProductItem from "@/components/ProductItem.vue";

const items: number[] = [];
for (let i = 1; i < 142; i++) {
  items.push(i);
}
</script>

<template>
  <div style="display: flex; flex-wrap: wrap; justify-content: space-between;">
    <ProductItem v-for="item in items" :key="item" :id="item" />
  </div>
</template>
