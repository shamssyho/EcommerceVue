<template>
    {{ cart }}

    <v-card class="mx-auto" max-width="344">
        <v-img :src="images[0]" height="200px" cover></v-img>
        <v-card-title>
            {{ id }} . {{ title }}
        </v-card-title>
        <v-card-subtitle>
            {{ stock }} in stock
        </v-card-subtitle>

        <v-card-actions>
            <v-btn color="indigo" @click="sendEvent">
                Add to cart
            </v-btn>


            <v-spacer></v-spacer>
            <v-btn color="indigo" :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'" @click="show = !show"></v-btn>
        </v-card-actions>

        <v-expand-transition>
            <div v-show="show">
                <v-divider></v-divider>

                <v-card-text>
                    {{ description }}
                </v-card-text>
            </div>
        </v-expand-transition>
    </v-card>
</template>
<script>
import { ref } from 'vue';
export default {
    name: "FormaCard",
    props: {
        id: Number,
        title: String,
        images: Array,
        description: String,
        price: Number,
        rating: Number,
        stock: Number,
    },

    // setup(props, context) {
    //     const show = ref(false);
    //     // const cart = ref([]);

        // function addToCart(product) {
        //     // Pass the index to the addToCart function
        //     cart.value.push(props.product);
        //     console.log(cart.value);
        // }
    //     function sendEvent(){
    //         context.emit('addToCart')
    //     }
    //     return {
    //         show,
    //         sendEvent,
    //         // addToCart,
    //         // cart,
    //     };
    // },
};


//     setup(props) {
//         const show = ref(false);
//         const cart = ref([]);

//         function addToCart(product) {
//             // Pass the index to the addToCart function
//             cart.value.push(props.product);
//             console.log(cart.value);
//         }

//         return {
//             show,
//             addToCart,
//             cart,
//         };
//     },
// };

</script>