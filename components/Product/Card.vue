
import type ProductDetailsVue from './ProductDetails.vue';
<template>
  <div class="container">
    <div
      class="flex-container"
      @click="openModal"
    >
      <DynamicImage
        class="image-cont"
        :imageUrl="data.image"
        :isProductView="true"
      />

      <ProductDetails class="details" :product="data" />
    </div>
  </div>
</template>

<script setup>
import { ref, defineEmits, defineProps } from "vue";
const props = defineProps(['data']);
const emits = defineEmits(['clickedButton']);
const openModal = () => {
  emits('clickedButton');
}
</script>

<style scoped>

.flex-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 16px;
  align-items: center;
  border-radius: 12px;
  border: 1px solid #e5e7ef;
  background: #fff;
  cursor: pointer;
}

.details {
  padding: 16px;
  width: 100%;
}

</style>