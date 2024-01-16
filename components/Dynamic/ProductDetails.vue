<template>
<div class="content">
    <div class="productDetails">
        <p class="text-body-large-regular regular name">
        {{ product.name }}
    </p>
    <p class="text-body-large-regular regular price">
        {{ product.price }}
    </p>
    </div>
    <div class="snippet">
        <p class="snip text-body-small-regular regular">
            {{ product.snippet }}
        </p>
    </div>
</div>
</template>

<script setup>
   import { ref, defineProps, defineEmits} from 'vue';
   const props = defineProps({
    product: {
        type: Object,
        required: true,
      },
   })
</script>

<style scoped>
.name{
    color: #303237;
    font-weight: 400;
}
.price{
    color: #303237;
    font-weight: 500;
}
.snip{
    color: #7E8494;
    font-weight: 400;
}
.productDetails{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.content{
    display: flex;
    flex-direction: column;
    gap: 8px;
    justify-content: center;
}
</style>
    
