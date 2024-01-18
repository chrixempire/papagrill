<template>
    <div class="container">
      <button class="minus" @click="decreaseQuantity">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
        >
          <path
            d="M6 12H18"
            stroke="#303237"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </button>
      <div class="quantity">
        <h4 class="text-heading-4-medium">{{ Quantity }}</h4>
      </div>
      <button class="plus" @click="increaseQuantity">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
        >
          <path
            d="M6 12H18"
            stroke="#303237"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M12 18V6"
            stroke="#303237"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </button>
    </div>
  </template>
  
  <script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
  quantity: {
    type: Number,
    required: true,
  },
});

const Quantity = ref(props.quantity);

const increaseQuantity = () => {
  Quantity.value += 1;
};

const decreaseQuantity = () => {
  if (Quantity.value > 0) {
    Quantity.value -= 1;
  }
};
  </script>
  
  <style scoped>
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  .plus,
  .minus {
    display: flex;
    width: 48px;
    height: 48px;
    padding: 10px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
    border-radius: 100px;
    background: var(--GREY-GREY6);
  }
  .quantity {
    display: flex;
    width: 48px;
    height: 48px;
    padding: 10px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 10px;
  }
  .quantity h4 {
    color: var(--GREY-GREY1);
  }
  </style>
  