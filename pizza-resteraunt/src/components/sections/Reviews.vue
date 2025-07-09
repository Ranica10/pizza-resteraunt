<script setup>
import reviews from '/src/assets/data/Reviews.json';

var totalReview = 0;

for (let i = 0; i < reviews.length; i++) {
    totalReview += reviews[i].review
}

const avgReview = totalReview / reviews.length

// Stars
var filledStars = Math.floor(avgReview)
const remainder = avgReview % 1

</script>

<template> 
    <div class="reviews-section">
        <h4>Reviews</h4>
        <div class="header-wrapper">
            <p class="avg-review">{{ avgReview }}</p>
            <div class="review-summary">
                <div class="review-stars">
                    <svg class="filled-star" v-for="star in filledStars" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                        <path fill="#bd3030" d="m12 16.102l-3.63 2.192q-.16.079-.297.064q-.136-.016-.265-.094q-.13-.08-.196-.226t-.012-.319l.966-4.11l-3.195-2.77q-.135-.11-.178-.263t.019-.293t.165-.23q.104-.087.28-.118l4.216-.368l1.644-3.892q.068-.165.196-.238T12 5.364t.288.073t.195.238l1.644 3.892l4.215.368q.177.03.281.119q.104.088.166.229q.061.14.018.293t-.178.263l-3.195 2.77l.966 4.11q.056.171-.011.318t-.197.226q-.128.08-.265.095q-.136.015-.296-.064z" />
                    </svg>
                    <div class="unfilled-stars" style="width: calc(((5 - filledStars)) * 24px);">
                        <svg class="unfilled-star" v-for="star in (5 - filledStars)" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                            <path fill="#bd3030" d="m8.85 16.825l3.15-1.9l3.15 1.925l-.825-3.6l2.775-2.4l-3.65-.325l-1.45-3.4l-1.45 3.375l-3.65.325l2.775 2.425zm3.15-.723l-3.63 2.192q-.16.079-.297.064q-.136-.016-.265-.094q-.13-.08-.196-.226t-.012-.319l.966-4.11l-3.195-2.77q-.135-.11-.178-.263t.019-.293t.165-.23q.104-.087.28-.118l4.216-.368l1.644-3.892q.068-.165.196-.238T12 5.364t.288.073t.195.238l1.644 3.892l4.215.368q.177.03.281.119q.104.088.166.229q.061.14.018.293t-.178.263l-3.195 2.77l.966 4.11q.056.171-.011.318t-.197.226q-.128.08-.265.095q-.136.015-.296-.064zm0-3.852" />
                        </svg>
                        <div class="remainder-star" v-if="remainder > 0" style="width: 12px;">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                                <path fill="#bd3030" d="m12 16.102l-3.63 2.192q-.16.079-.297.064q-.136-.016-.265-.094q-.13-.08-.196-.226t-.012-.319l.966-4.11l-3.195-2.77q-.135-.11-.178-.263t.019-.293t.165-.23q.104-.087.28-.118l4.216-.368l1.644-3.892q.068-.165.196-.238T12 5.364t.288.073t.195.238l1.644 3.892l4.215.368q.177.03.281.119q.104.088.166.229q.061.14.018.293t-.178.263l-3.195 2.77l.966 4.11q.056.171-.011.318t-.197.226q-.128.08-.265.095q-.136.015-.296-.064z" />
                            </svg>
                        </div>
                    </div>
                </div>
                <p class="total-reviews">{{ reviews.length }} ratings</p>
            </div>
        </div>
        <div class="reviews-wrapper">
            <div class="review" v-for="(review, index) in reviews">
                <p>{{ review.name }}</p>
                <p>{{ review.review }} / 5</p>
                <p>{{ review.review_title }}</p>
                <p>{{ review.review_description }}</p>
            </div>
        </div>
    </div>
</template>