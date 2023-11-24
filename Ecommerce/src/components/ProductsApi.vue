<template>
    <div class="form-card">
        <FormCard v-for="product in products" :key="product.id"
            :id="product.id" :title="product.title" :images="product.images" :description="product.description"
            :price="product.price" :rating="product.rating" :stock="product.stock"
            @addToCart="addToCart"
            />
    </div>
</template>

<script>
import FormCard from './FormCard.vue';

import axios from 'axios';
import { ref, onMounted } from 'vue'
export default {
    name: "ProductsApi",
    components: {
        FormCard,
    },

    props: [],
    setup() {
        const products = ref([]);
        const cart = ref([]);
        function getProducts() {
            axios.get('https://dummyjson.com/products')
                .then((response) => {
                    products.value = response.data.products
                })
                .catch((error) => {
                    console.error('Error fetching products:', error);
                });
        }
        function addToCart(product){
            cart.value.push(product)
            console.log(cart)
        }
        onMounted(getProducts);


        return {
            getProducts,
            products,
            addToCart
        }
    }
}
</script>
<style>
.form-card {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
</style>


