<script setup>
import reviews from '/src/assets/data/Reviews.json';
import ReviewStars from '../partials/ReviewStars.vue';

var totalReview = 0;

for (let i = 0; i < reviews.length; i++) {
    totalReview += reviews[i].review
}

const avgReview = totalReview / reviews.length

</script>

<template> 
    <div class="reviews-section">
        <h4>Reviews</h4>
        <div class="header-wrapper">
            <p class="avg-review">{{ avgReview }}</p>
            <div class="review-summary">
                <ReviewStars :review="avgReview" ></ReviewStars>
                <p class="total-reviews">{{ reviews.length }} ratings</p>
            </div>
        </div>
        <div class="reviews-wrapper">
            <div class="review" v-for="(review, index) in reviews">
                <p>{{ review.name }}</p>
                <ReviewStars :review="review.review" ></ReviewStars>
                <p>{{ review.review_title }}</p>
                <p>{{ review.review_description }}</p>
            </div>
        </div>
    </div>
</template>