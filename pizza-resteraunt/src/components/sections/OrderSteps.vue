<script setup>

const steps = ["Choose", "Customize", "Order", "Delivery"]


</script>

<template>
    <div class="order-steps-section">
        <h4 style="margin-bottom: 28px; font-size: 48px;">How It Works</h4>
        <div class="steps">
            <div class="step" v-for="(step, index) in steps">
                <h4 class="step-index">{{ index + 1 }}</h4>
                <p class="step-name">{{ step }}</p>
            </div>
        </div>
    </div>
</template>