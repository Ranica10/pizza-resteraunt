<script setup>
import Navbar from './components/Navbar.vue';

import Intro from './components/sections/Intro.vue';
import Highlights from './components/sections/Highlights.vue';

</script>

<template>
    <div class="app">
        <Navbar></Navbar>
        <div class="nav-spacer" style="height: 72px;"></div>
        <Intro></Intro>
        <Highlights></Highlights>
    </div>
</template>