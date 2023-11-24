<template>
    <h1>Cart</h1>
    <ProductsApi />
    <!-- <FormCard /> -->
  </template>
  
  <script>
  import ProductsApi from '@/components/ProductsApi.vue';
  export default {
    name : "Cart", 
    components : {
      ProductsApi,
    }
  }
  </script>
  