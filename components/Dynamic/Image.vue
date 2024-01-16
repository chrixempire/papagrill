<template>
    <img
      :src="imageUrl"
      alt="Dynamic Image"
      :style="{ borderRadius: isModalView ? '12px' : '12px 12px 0 0' }"
    />
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  
  const props = defineProps(['imageUrl', 'isModalView']);
  </script>

  <style scoped>
img {
  width: 100%;
  height: auto;
}
  </style>
  
  