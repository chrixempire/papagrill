
import type ProductDetailsVue from './ProductDetails.vue';
<template>
  <div class="container">
    <div
      class="flex-container"
      v-for="(product, index) in products"
      :key="index"
      @click="openModal"
    >
      <DynamicImage
        class="image-cont"
        :imageUrl="product.image"
        :isModalView="false"
      />

      <DynamicProductDetails class="details" :product="product" />
    </div>
  </div>
</template>

<script setup>
import { ref, defineEmits } from "vue";
const productImageUrl = "images/chickenimage.jpg";
const products = [
  {
    name: "Classic beef burger",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/chickenimage.jpg",
  },
  {
    name: "French fries",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/bacon.jpg",
  },
  {
    name: "Chicken and bacon",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/pap.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
  {
    name: "Naija breakfast",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/philly.jpg",
  },
];
const emits = defineEmits(['clickedButton']);
const openModal = () => {
  emits('clickedButton');
}
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px 28px; 
}

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