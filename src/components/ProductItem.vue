<script setup lang="ts">
import { ref } from "vue";
//${props.id}
const props = defineProps({
  id: Number,
  newImages: Boolean
});

const imageUrl = new URL(`../assets/images/${props.id}.jpeg`, import.meta.url).href;
const newUrl = new URL(`../assets/brecho/${props.id}.jpg`, import.meta.url).href;

const error = ref(false);

function setError() {
  error.value = true;
}
</script>
<template>
  <div v-if="!newImages" style="margin: 1rem">
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
  <div v-else style="margin: 1rem">
    <img
      style="object-fit: cover"
      height="200"
      width="200"
      @error="setError()"
      :src="newUrl"
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
