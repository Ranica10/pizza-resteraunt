<script setup>
import { ref } from 'vue';
import pizzaIcon from '../assets/imgs/pizza-icon.png'
import cart from '../assets/imgs/cart.svg'

const pages = ref([
    { name: 'Home', path: '/' },
    { name: 'Menu', path: '/menu' },
    { name: 'Order', path: '/order' },
    { name: 'Contact', path: '/contact' }
]);

</script>

<template>
    <nav>
        <div class="nav-container">
            <div class="logo">
                <img :src="pizzaIcon"/>
                <p>La Crosta</p>
            </div>
        
            <ul>
                <li v-for="page in pages" :key="page.name">{{ page.name }}</li>
            </ul>

            <div class="action-items">
                <img :src="cart" class="cart"/>
            </div>
        </div>
    </nav>
</template>