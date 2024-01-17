<template>
    <div class="total-container">
      <div class="header">
        <h3 class="heading-3-bold bold">Select your branch</h3>
      </div>
      <div class="hold">
        <div class="list-container" v-for="(location, index) in locations" :key="index">
          <SelectList
          class="list-item"
            :data="location"
            :selectedItem="selectedCard"
            @selectItem="selectItem"
          />
        </div>
      </div>
      <div class="btn">
        <button class="text-body-large-medium medium">Continue</button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  const locations = [
    { label: "Yaba", value: "Yaba" },
    { label: "Ikeja", value: "Ikeja" },
    { label: "Ikorodu", value: "Ikorodu" },
    { label: "Lekki", value: "Lekki" },
    { label: "Abuja", value: "Abuja" },
  ];
  const selectedCard = ref("");
  const selectItem = (value) => {
    selectedCard.value = value;
    console.log(value);
  };
  </script>
  
  <style scoped>
  .total-container {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 40px;
    flex-direction: column;
    width: 330px;
  }
  
  .hold {
    width: 100%;
  }
  
  h3 {
    color: #303237;
    font-size: 24px;
    font-style: normal;
    font-weight: 600;
    line-height: 36px;
    letter-spacing: -0.5px;
  }
  
  button {
    display: flex;
    height: 48px;
    padding: 16px 24px;
    justify-content: center;
    align-items: center;
    gap: 8px;
    align-self: stretch;
    border-radius: 100px;
    background: #121212;
    color: #fff;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    width: 100%;
  }
  button:hover{
    background:  #303237;
  }
  
  button:focus{
    background:  #121212;;
  }
  
  .btn {
    width: 100%;
  }
  .hold{
    display: flex;
    flex-direction: column;
    gap: 12px;
    justify-content: center;
  }
  </style>