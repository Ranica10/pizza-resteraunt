<script setup>
import { ref, computed } from 'vue'

import pizzas from '/src/assets/data/Pizzas.json';

const popularNames = ["Margherita", "Pepperoni", "BBQ Chicken", "Meat Lovers", "Veggie Supreme"]
const popularPicks = pizzas.filter(pizza => popularNames.includes(pizza.name))

const currentIndex = ref(popularPicks.length - 1)
const visibleCount = 3

const visiblePizzas = computed(() => {
    const result = [];

    for (let i = 0; i < visibleCount; i++) {
        result.push(popularPicks[(currentIndex.value + i) % popularPicks.length]);
    }

    return result;
});

function next() {
    currentIndex.value = (currentIndex.value + 1) % popularPicks.length;
}

function back() {
    currentIndex.value = (currentIndex.value - 1 + popularPicks.length) % popularPicks.length;
}
</script>

<template>
    <div class="highlights-section">
        <h2>Popular Picks</h2>

        <div class="carousel">
            <button class="arrow-btn back" @click="back">
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24">
                    <path fill="#FFFFFF" d="M15.41 16.58L10.83 12l4.58-4.59L14 6l-6 6l6 6z" />
                </svg>
            </button>

            <div class="popular-picks">
                <div v-for="(pizza, index) in visiblePizzas" :key="pizza.name" class="pizza"
                :class="index === 1 ? 'active-pizza' : 'inactive-pizza'">
                    <img :src="pizza.image" :alt="pizza.name">
                    <p class="pizza-name">{{ pizza.name }}</p>
                    <p class="pizza-cost">$ {{ pizza.price }}</p>
                </div>
            </div>

            <button class="arrow-btn next" @click="next">
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" viewBox="0 0 24 24">
                    <path fill="#FFFFFF" d="M8.59 16.58L13.17 12L8.59 7.41L10 6l6 6l-6 6z" />
                </svg>
            </button>
        </div>
    </div>
</template>