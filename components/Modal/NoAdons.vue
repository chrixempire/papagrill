<template>
  <div class="container">
    <div class="modal-content">
      <div class="cancel-btn">
        <button>
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="17" viewBox="0 0 16 17" fill="none">
  <path d="M3.3335 13.6361L12.6668 4.30273M3.3335 4.30273L12.6668 13.6361L3.3335 4.30273Z" stroke="#433955" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
        </button>
      </div>
    <div class="image-cont">
        <DynamicImage
          :imageUrl="data.image"
          :isModalView ="true"
        />
    </div>
    <div class="product-details">
        <ProductDetails class="details" :product="data" />
      <div class="btn-ctn">
        <ProductCounterBtn :quantity="quantity" class="count" />
        <DynamicButton
        class="bolder text-button-standard standard"
        @clickButton="addToCart"
          buttonText="Add"
          :buttonPrice="buttonPrice"
          :isLoading="isLoading"
          :showText="true"
          size="standard"
          type="primary"
        />
      </div>  
    </div>
    </div>  
  </div>  
</template>  
  
<script setup>  
import { ref, defineEmits, defineProps } from "vue";
const props = defineProps(['data']);
const quantity = ref(0);
const isLoading = ref(false);
const addToCart = () => {
    console.log('work')
}
const buttonPrice = props.data.price
</script>  
  
<style scoped>  

.cancel-btn button {  
  display: flex;
  width: 48px;
  height: 48px;
  padding: 16px 24px;
  justify-content: center;
  align-items: center;
  gap: 8px;
  border-radius: 100px;
  background: var(--GREY-GREY6);
  margin-left: auto;
}
.btn-ctn{
    display: flex;
    align-items: center;
    gap: 48px;
    width: 100%;
}

button svg{
    width: 16px;
    height: 16px;
}
.image-cont{
    padding: 16px 0px;
}
.product-details{
    padding: 16px 0px;
    display: flex;
    justify-content: center;
    gap: 48px;
    flex-direction: column;
}
</style>