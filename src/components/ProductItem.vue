<script setup lang="ts">
import { ref } from "vue";
//${props.id}
const props = defineProps({
  id: Number,
});

const imageUrl = new URL(`../assets/images/${props.id}.jpeg`, import.meta.url).href;
const error = ref(false);

function setError() {
  error.value = true;
}
</script>
<template>
  <div style="margin: 1rem">
    <img
      style="object-fit: cover"
      height="200"
      width="200"
      @error="setError()"
      :src="imageUrl"
    />
    <div
      style="
        background-color: rgba(255, 255, 255, 0.5);
        color: rgba(0, 0, 0, 0.8);
      "
    >
      <h1>{{ id }}</h1>
    </div>
  </div>
</template>
