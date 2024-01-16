<template>
    <div @click="selectItem(card.value)" class="container">
      <label class="text-body-large-regular regular ">{{ card.label }}</label>
      <svg class="circle" :class="{ selected: isSelected }"  xmlns="http://www.w3.org/2000/svg" width="20" height="20"
          viewBox="0 0 20 20" fill="none">
          <rect x="2.50033" y="2.50002" width="15" height="15" rx="7.5" fill="white" stroke="#E4E7EC"
            stroke-width="1.66667" />
        </svg>
        <svg class="try" v-if="isSelected" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20"
          fill="none">
          <path
            d="M10.0003 1.66666C5.40866 1.66666 1.66699 5.40832 1.66699 9.99999C1.66699 14.5917 5.40866 18.3333 10.0003 18.3333C14.592 18.3333 18.3337 14.5917 18.3337 9.99999C18.3337 5.40832 14.592 1.66666 10.0003 1.66666ZM13.9837 8.08332L9.25866 12.8083C9.14199 12.925 8.98366 12.9917 8.81699 12.9917C8.65033 12.9917 8.49199 12.925 8.37533 12.8083L6.01699 10.45C5.77533 10.2083 5.77533 9.80832 6.01699 9.56666C6.25866 9.32499 6.65866 9.32499 6.90033 9.56666L8.81699 11.4833L13.1003 7.19999C13.342 6.95832 13.742 6.95832 13.9837 7.19999C14.2253 7.44166 14.2253 7.83332 13.9837 8.08332Z"
            fill="#09420C" />
        </svg>
    </div>
  </template>
  
  <script setup>
   import { ref, defineProps, defineEmits, computed } from 'vue';
   const props = defineProps({
    card: {
        type: Object,
        required: true,
      },
      selectedItem: {
        type: String,
        required: true,
      },
   })
   const isSelected = computed(() => {
  return props.selectedItem === props.card.value;
});

const emits = defineEmits(['selectItem']);
const selectItem = (value) => {
  emits('selectItem', value);
};
  </script>


<style scoped>
  .selected.circle {
    stroke: none;
    fill:black;
    display: none;
  }
  
  svg circle {
    stroke: var(--grey-200);
    stroke-width: 1px;
    fill: none;
    width: 20px;
    height: 20px;
  }
  label{
    color: #303237;
  }
  .container{
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
  