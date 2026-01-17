<script lang="ts">
import ProductCard from './ProductCard.vue';
import Cart from './Cart.vue';
import type { CartDetail, Product } from './types';

    export default {
        components: {
            ProductCard,
            Cart
        },
        data() {
            return {
                products: <Array<Product>>[
                    { name: 'Silla', price: 10, id: 1 },
                    { name: 'Escritorio', price: 15, id: 2 },
                    { name: 'Monitor', price: 20, id: 3 },
                    { name: 'Microfono', price: 30, id: 4 }
                ],
                details: <Array<CartDetail>>[]
            };
        },
        methods: {
            onProductAdded(productId: number) {
                const detailFound = this.details.find(
                    (d) => d.productId === productId
                );
                if (detailFound) {
                    detailFound.quantity += 1;
                } else {
                    this.details.push({ productId, quantity: 1 });
                }
            }
        }
    }
</script>
<template>
    <ProductCard 
    v-for="p in products" 
    :key="p.name" 
    :product="p" 
    @addProduct="onProductAdded(p.id)"/>
    <Cart :details="details"/>
</template>