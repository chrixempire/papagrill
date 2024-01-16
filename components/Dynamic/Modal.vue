
<template>
  <div v-if="showModal" class="modal-overlay" @click="closeModal">
    <div class="modal-container" @click.stop>
      <div class="modal-content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>


<script setup>

import { ref, defineProps } from 'vue';
   const props = defineProps({
   showModal: {
        type: Boolean,
        required: true,
      },
   })

   const emits = defineEmits(['closeModal']);
const closeModal = () => {
  emits('closeModal');
}
</script>

<style>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); /* Grey overlay */
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-container {
  background: white;
  padding: 20px;
  border-radius: 16px;
background: white;
box-shadow: 0px 1px 3px 0px rgba(50, 50, 71, 0.10), 0px 0px 1px 0px rgba(12, 26, 75, 0.20);

width: 400px;
height: 400px;
}
.modal-content{
    width: 100%;
}
@media screen and (max-width: 650px) {
    .modal-overlay {
        position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); /* Grey overlay */
  display: flex;
  align-items: flex-end;
  justify-content: center;

    }
    .modal-container{
        width: 100%;
        display: flex;
        padding:24px;
        border-radius: 24px 24px 0px 0px;
        border: 1px solid red;

     
    }
}
</style>