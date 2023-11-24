<template>
  <h1>Home</h1>
  <ProductsApi />
  <!-- <FormCard /> -->
</template>

<script>
import ProductsApi from '@/components/ProductsApi.vue';
import FormCard from '@/components/FormCard.vue';
export default {
  name : "Home", 
  components : {
    ProductsApi,
    FormCard,
  }
}
</script>
