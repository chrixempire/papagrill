<template>
<div class="onCreated">
  <ModalMain :showModal="showCreatedModal" @closeModal="closeModal">
  <ModalLocation @NextPage="closedModal"/>
  </ModalMain>
</div>
  <div class="overall">
    <div class="product-ctn">
      <div class="product">
        <ProductCard
          v-for="(product, index) in products"
          :key="index"
          :data="product"
          @clickedButton="openModal(product.addons)"
        />
      </div>
      <LoaderWeb v-if="!products.length" />
    </div>
    <ModalMain :showModal="showModal" @closeModal="closeModal">
      <div class="list">
        <ModalNoAdons
          v-for="(modal, index) in modals"
          :key="index"
          :data="modal"
          :Addons="modalAddons"
          :closed="closeModal"
        />
      </div>
    </ModalMain>
  </div>
</template>
  
  <script setup>
import { ref, onMounted } from "vue";
const modals = [
  {
    name: "Classic beef burger",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/chickenimage.jpg",
  },
];
const products = [
  {
    name: "Classic beef burger",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/chickenimage.jpg",
    addons:true
  },
  {
    name: "French fries",
    snippet: "Classic sub",
    price: "₦3,500",
    image: "images/bacon.jpg",
    addons:false
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
const showCreatedModal = ref(false);

const modalAddons = ref('');

const openModal = (addons) => {
  modalAddons.value = addons; 
  showModal.value = true;
};
const closeModal = () => {
  showModal.value = false;
};
const closedModal = () => {
  showCreatedModal.value = false;
};
onMounted(() => {
  // Display the modal when the component is mounted
  showCreatedModal.value = true;
});
</script>
  
  <style scoped>
.overall {
  margin: 50px;
}
.list {
  width: 100%;
}
.product {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 24px 28px;
}
.image {
  margin: 25px;
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  gap: 30px;
}
@media screen and (max-width: 650px) {
  .overall {
    margin: 0px;
    padding: 20px;
  }
}
</style>
  