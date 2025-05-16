<script setup>
import { ref } from 'vue';
import pizzaIcon from '../assets/imgs/pizza-icon.svg'
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
        <div class="logo">
            <img :src="pizzaIcon"/>
            <p>Pizza</p>
        </div>
    
        <ul>
            <li v-for="page in pages" :key="page.name">{{ page.name }}</li>
        </ul>

        <div class="action-items">
            <img :src="cart"/>
        </div>
    </nav>
</template>

<style lang="scss">
@use "../styles/_variables";

nav {
    display: flex;
    width: 90%;
    padding: 0px 16px;
    justify-content: space-between;
    align-items: center;
    background: #2A2A2A;

    position: fixed;
    top: 6px;
    left: 50%;
    transform: translateX(-50%);
    z-index: 1000;

    .logo {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 15px;

        img {
            scale: 1.8;
        }

        p {
            color: #FFF;
            font-family: variables.$fancy-cursive;
            font-size: 19px;
            letter-spacing: 3px;
        }
    }

    ul {
        list-style: none;
        display: flex;
        align-items: center;
        gap: 40px;

        li {
            justify-content: center;
            gap: 10px;
            cursor: pointer;

            color: #dddddd;
            font-family: variables.$heading;
            font-size: 19px;
            font-weight: 400;

            transition: transform 0.2s ease-in-out;

            &:hover {
                transform: scale(1.08);
                color: #ffffff;
            }

            &:focus {
                color: #ffffff;
            }

            &::after {
                content: '';
                height: 2px;
                width: 100%;
                background: #bd3030;
                position: absolute;
                left: 0;
                bottom: -2px;
                opacity: 0;
                transition: all 0.2s;
                pointer-events: none;
            }

            &:hover::after, &:focus::after {
                opacity: 1;
            }
        }
    }

    .action-items {
        cursor: pointer;
        transition: transform 0.2s ease-in-out;

        &:hover {
            transform: scale(1.1);
        }

        &::after {
            content: '';
            height: 2px;
            width: 100%;
            background: #bd3030;
            position: absolute;
            left: 0;
            bottom: -2px;
            opacity: 0;
            transition: all 0.2s;
            pointer-events: none;
        }

        &:hover::after, &:focus::after {
            opacity: 1;
        }
    }
}


</style>