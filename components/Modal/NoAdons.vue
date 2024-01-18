<template>
  <div class="container">
    <div class="modal-content">
      <div class="cancel-btn">
        <div class="cancel" @click="closed">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="17"
            viewBox="0 0 16 17"
            fill="none"
          >
            <path
              d="M3.3335 13.6361L12.6668 4.30273M3.3335 4.30273L12.6668 13.6361L3.3335 4.30273Z"
              stroke="#433955"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </div>
      </div>
      <div class="image-cont">
        <DynamicImage :imageUrl="data.image" :isModalView="true" />
      </div>
      <div class="product-details">
        <ProductDetails class="details" :product="data" />

        <div class="Addons" v-if="Addons">
          <div class="selective">
            <p class="text-body-small-medium medium">SELECT TYPE</p>
            <div class="flexed-select">
              <div
                class="select-type"
                v-for="(select, index) in Selects"
                :key="index"
              >
                <SelectList
                  :data="select"
                  :selectedItem="selectedCard"
                  @selectItem="selectItem"
                >
                  <DynamicImage :imageUrl="select.image" :isModalView="true" />
                </SelectList>
              </div>
            </div>
          </div>
          <div class="addMore">
            <div class="added">
              <p class="text-body-small-medium medium">ADD ADD-ONS</p>
              <div class="multiChoice">
                <DynamicMultiChoice
                  v-for="food in foods"
                  :key="food.name"
                  :name="food.name"
                  :price="food.price"
                  @checkboxChange="handleCheckboxChange"
                />
              </div>
            </div>
          </div>
        </div>

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
const Selects = [
  { label: "Barbecue", value: "Barbecue", image: "images/chickenimage.jpg" },
  { label: "Peppered", value: "Peppered", image: "images/chickenimage.jpg" },
];
const foods = [
  { name: "Ketchup", price: 100 },
  { name: "Burger", price: 150 },
  { name: "Salad", price: 150 },
  { name: "Pasta", price: 100 },
];
const selectedCard = ref("");
const isLoading = ref(false);
const selectItem = (value) => {
  selectedCard.value = value;
  console.log(value);
};
const props = defineProps(["data", 'Addons', 'closed']);
const quantity = ref(0);
const addToCart = () => {
  console.log("work");
};
const buttonPrice = props.data.price;
const handleCheckboxChange = ({ price, selected }) => {
  console.log(price)
};
</script>  
  
<style scoped>
.cancel{
  /* border: 1px solid red; */
background: var(--GREY-GREY6);
width:  48px;
height: 48px;
display: flex;
justify-content: center;
align-items: center;
border-radius: 100px;
margin-left: auto;
cursor: pointer;
}
.cancel svg{
  /* border: 1px solid blue; */
  

}
.btn-ctn {
  display: flex;
  align-items: center;
  gap: 48px;
  width: 100%;
}

button svg {
  width: 16px;
  height: 16px;
}

.image-cont {
  padding: 16px 0px;
}

.product-details {
  padding: 16px 0px;
  display: flex;
  justify-content: center;
  gap: 48px;
  flex-direction: column;
}

.selective p {
  color: var(--GREY-GREY1);
}
.added {
  display: flex;
  flex-direction: column;
  gap: 32px;
  /* justify-content: center; */
  align-items: flex-start;
}
.selective {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-direction: column;
}

.select-type {
  width: 224px;
}

.flexed-select {
  display: flex;
  justify-items: center;
  align-items: center;
  gap: 24px;
}
.multiChoice {
  width: 100%;
  display: flex;
  gap: 32px;
  flex-direction: column;
}
.Addons {
  display: flex;
  justify-content: space-between;
  gap: 48px;
  flex-direction: column;
}
</style>