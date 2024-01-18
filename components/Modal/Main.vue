
<template>
    <div v-if="showModal" :class="{ 'modal-overlay': true, 'show-modal': showModal }"  >
      <div :class="{ 'modal-container': true, 'show-modal': showModal }" @click.stop>
        <div class="modal-content">
          <slot :closeModal="closeModal"></slot>
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
    background: rgba(0, 0, 0, 0.5); 
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0; 
    transition: opacity 0.5s ease-in; 
    overflow: hidden;
  }
  
  .modal-container {
    max-height: 90%;
    background: white;
    padding: 16px;
    border-radius: 16px;
  background: white;
  /* box-shadow: 0px 1px 3px 0px rgba(50, 50, 71, 0.10), 0px 0px 1px 0px rgba(12, 26, 75, 0.20); */
  opacity: 0;
    transition: opacity 0.5s ease-in;
    overflow-y: auto;
    /* overflow: hidden; */
  }


  .modal-content{
      width: 100%;
      overflow-y: auto;
  }
  .show-modal {
    opacity: 1;
  }
  @media screen and (max-width: 650px) {
      .modal-overlay {
          position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5); 
    display: flex;
    align-items: flex-end;
    justify-content: center;
  
      }
      .modal-container{
          width: 100%;
          display: flex;
          padding:24px;
          border-radius: 24px 24px 0px 0px;
  
       
      }
  }
  </style>