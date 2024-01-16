<template>
    <div class="total">
        <div class="product">
            <DynamicProductCard @clickedButton="openModal"/>
        </div>
       <div class="image">
        <DynamicImage :imageUrl="modalImageUrl" :isModalView="true" />
        <DynamicImage :imageUrl="productImageUrl" :isModalView="false" />
       </div>
      <DynamicModal :showModal="showModal" @closeModal="closeModal">
        <div class="list" >
          <LocationModal/>
        </div>
      </DynamicModal>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const showModal = ref(false);
  const modalImageUrl = 'images/meat.jpg';
  const productImageUrl = 'images/chickenimage.jpg';
  const cards = [
    { label: 'Yaba', value: 'Yaba' },
    { label: 'Ikeja', value: 'Ikeja' },
    { label: 'Ikorodu', value: 'Ikorodu' },
    { label: 'Lekki', value: 'Lekki' },
    { label: 'Abuja', value: 'Abuja' },
  ];
  
  const selectedCard = ref("");
  const selectItem = (value) => {
    selectedCard.value = value;
    console.log(value)
  };

  const openModal = () => {
    showModal.value = true
  }
  const closeModal = () => {
    showModal.value = false
  }
  </script>
  
  <style scoped>
  .total{
    padding: 80px;
  }
  .list{
    width: 100%;
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
  