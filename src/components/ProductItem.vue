<script setup>
import { ref } from "vue";

const props = defineProps({
  id: Number,
});
const error = ref(false);

function setError() {
  this.error = true;
}
</script>
<template>
  <div v-if="!error" style="margin: 1rem">
    <img    
      style="object-fit: cover"
      height="200"
      width="200"
      @error="setError()"
      :src="`src/assets/images/${id}.jpeg`"
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
