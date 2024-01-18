<template>
  <div class="total">
    <DynamicMultiChoice
    v-for="food in foods"
      :key="food.name"
      :name="food.name"
      :price="food.price"
      @checkboxChange="handleCheckboxChange"
    />
    <div class="total-price">Total Price: {{ totalPrice }}$</div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const foods = [
  { name: 'Pizza', price: 10 },
  { name: 'Burger', price: 5 },
  { name: 'Salad', price: 8 },
  { name: 'Pasta', price: 12 },
];

const totalPrice = ref(0);

const handleCheckboxChange = ({ price, selected }) => {
  totalPrice.value += selected ? price : -price;
};

</script>

<style scoped>
.total-price {
  margin-top: 10px;
  font-weight: bold;
}
.total{
  margin: 30px;
  width: 350px;
}
</style>
