<script setup lang="ts">
import ProductItem from "@/components/ProductItem.vue";
import { ref, computed } from "vue";

import {
  BRINQUEDOS,
  ELETRODOMESTICOS,
  AUDIOVISUAL,
  ANTIGUIDADES,
  COZINHA,
  DECORACAO,
  MOVEIS,
  COSTURA,
} from "@/data/filters.js";

const items: number[] = [];
const showNew = ref(true);

const itemsCount = computed(() => {
  const count = showNew.value ? 342 : 163;
  let items = [];
  for (let i = 1; i < count; i++) {
    items.push(i);
  }
  return items;
});
</script>

<template>
  <button @click="showNew = !showNew">
    {{ showNew ? "ver antigos" : "ver novos" }}
  </button>
  <div v-if="showNew">
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem
        v-for="item in itemsCount"
        :key="item"
        :id="item"
        new-images
      />
    </div>
  </div>
  <div v-else>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in itemsCount" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in BRINQUEDOS" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in ELETRODOMESTICOS" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in AUDIOVISUAL" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in ANTIGUIDADES" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in COZINHA" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in DECORACAO" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in MOVEIS" :key="item" :id="item" />
    </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between">
      <ProductItem v-for="item in COSTURA" :key="item" :id="item" />
    </div>
  </div>
</template>
