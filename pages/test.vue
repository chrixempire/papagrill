<template>
    <div><LoaderWeb/></div>
    <div><ProductCounterBtn :quantity="quantity"/></div>
    <button @click="logQuantity">Log Quantity</button>
</template>
<script setup>
import { ref } from 'vue';

const quantity = ref(0);

const logQuantity = () => {
  console.log('Quantity:', quantity.value);
};
</script>

<style scoped>

</style>