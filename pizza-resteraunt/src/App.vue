<script setup>
import Navbar from './components/Navbar.vue';

import Intro from './components/sections/Intro.vue';
import Highlights from './components/sections/Highlights.vue';
import OrderSteps from './components/sections/OrderSteps.vue';
import Reviews from './components/sections/Reviews.vue';

</script>

<template>
    <div class="app">
        <Navbar></Navbar>
        <div class="nav-spacer" style="height: 72px;"></div>
        <Intro></Intro>
        <Highlights></Highlights>
        <div class="spacer" style="height:40px"></div>
        <OrderSteps></OrderSteps>
        <Reviews></Reviews>
    </div>
</template>