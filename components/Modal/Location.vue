<template>
    <div class="total-container">
      <div class="header">
        <h3 class="text-heading-3-bold bold text-grey1">Select your branch</h3>
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
        <DynamicButton
        class="bold text-button-standard standard"
          @clickButton="NextPage"
          buttonText="Continue"
          :isLoading="isLoading"
          :showText="true"
          size="standard"
          type="primary"
        />
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref,defineEmits} from "vue";
  const locations = [
    { label: "Yaba", value: "Yaba" },
    { label: "Ikeja", value: "Ikeja" },
    { label: "Ikorodu", value: "Ikorodu" },
    { label: "Lekki", value: "Lekki" },
    { label: "Abuja", value: "Abuja" },
  ];
  const selectedCard = ref("");
  const isLoading = ref(false);
  const selectItem = (value) => {
    selectedCard.value = value;
    console.log(value);
  };

  const emit = defineEmits()
  const NextPage = () => {
    emit('NextPage')
    console.log('work')
  }
  </script>
  
  <style scoped>
  .total-container {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    gap: 40px;
    flex-direction: column;
    width: 330px;
  }
  
  .hold {
    width: 100%;
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