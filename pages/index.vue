<template>
    <div class="total">
        <div class="product-ctn">
          <div class="product">
            <ProductCard  v-for="(product, index) in products" :key="index" :data="product" @clickedButton="openModal"/>
        </div>
        <LoaderWeb v-if="!products.length"/>
        </div>
      <ModalMain :showModal="showModal" @closeModal="closeModal">
        <div class="list" >
          <ModalNoAdons  v-for="(modal, index) in modals" :key="index" :data="modal "/>
        </div>
      </ModalMain>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const modals = [
  {
    name: "Classic beef burger",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/chickenimage.jpg",
  },
  ]
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
  const showModal = ref(false);

  const openModal = () => {
    showModal.value = true
  }
  const closeModal = () => {
    showModal.value = false
  }
  </script>
  
  <style scoped>

  .list{
    width: 100%;
  }
  .product{
    display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px 28px; 
  }
  .image{
    margin: 25px;
    width: 200px;
    height: 200px;
    display: flex;
    flex-direction: column;
    gap: 30px;
  }
@media screen and (max-width: 650px) {
    .total{
        padding: 20px;
    }
}
  </style>
  