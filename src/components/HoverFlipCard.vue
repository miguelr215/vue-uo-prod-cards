<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
	product: { type: Object, required: false },
});

const isFlipped = ref(false);

function toggleFlipped() {
	isFlipped.value = !isFlipped.value;
}
</script>

<template>
	<div class="hover-card" :class="{ flipped: isFlipped }" @mouseenter="toggleFlipped" @mouseleave="toggleFlipped">
		<div class="card-face card-front">
			<img :src="product.image[0]" :alt="product.name" />
		</div>

		<div class="card-face card-back">
            <span class="brand">{{ product.brand.name }}</span>
			<img :src="product.image[1]" :alt="product.name">
            <div class="card-back-content">
                <p>{{ product.name }}</p>
                <p>${{ product.offers.highPrice }}</p>
                <a :href="product.path" class="view-link">View &blacktriangleright;</a>
            </div>
		</div>
	</div>
</template>

<style scoped>
.hover-card {
	position: relative;
	width: 100%;
	max-width: 300px;
	min-height: 450px;
	margin: 0 auto 2rem;
	perspective: 150rem;
	-moz-perspective: 150rem;
}
.card-face {
	width: 100%;
	height: 100%;
	min-height: 450px;
	position: absolute;
	top: 0;
	left: 0;
	backface-visibility: hidden;
	-webkit-backface-visibility: hidden;
	overflow: hidden;
	box-shadow: 0 1.25rem 2.5rem rgba(0, 0, 0, 0.15);
	transition: all 0.8s ease;
}
.card-front img {
	width: 100%;
	height: auto;
}
.card-back {
	background: #ececec;
	transform: rotateY(180deg);
}
.hover-card.flipped .card-front {
	transform: rotateY(-180deg);
}
.hover-card.flipped .card-back {
	transform: rotateY(0);
}
.card-back .brand {
    position: absolute;
    top: 5px;
    right: 5px;
    color: #282277;
    font-size: 0.75rem;
    line-height: 1.1;
    background: rgba(255, 255, 255, 0.65);
    border-radius: 50px;
    padding: 0.25rem;
}
.card-back-content {
    width: 50%;
    background: rgba(255, 255, 255, 0.65);
    border-radius: 0.25rem;
    padding: 0.5rem;
    position: absolute;
    bottom: 5%;
    left: 50%;
    transform: translateX(-50%);
    font-size: 0.875rem;
    line-height: 1.2;
    text-align: center;
}
.card-back-content > p:nth-child(2) {
    font-size: 1rem;
    font-weight: 600;
    margin: 0.5rem 0;
}
.card-back .view-link {
	border: 0;
	background: transparent;
	color: #282277;
    text-decoration: none;
    
}
.card-back .view-link:hover {
    color: rgb(37, 135, 135);
}
.card-back img {
	width: 100%;
	height: auto;
}
@media (max-width: 350px) {
}
</style>
