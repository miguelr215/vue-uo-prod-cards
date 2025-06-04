<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
	product: { type: Object, required: false },
});

const isHovered = ref(false);

function toggleHovered() {
	isHovered.value = !isHovered.value;
}
</script>

<template>
	<figure
		class="zoom-card"
		:class="{ hovered: isHovered }"
		@mouseenter="toggleHovered"
		@mouseleave="toggleHovered"
		@keyup.enter="toggleHovered"
		aria-label="Hover Zoom Card"
		tabindex="0"
	>
		<h3 class="prod-brand">{{ product.brand.name }}</h3>
		<img :src="product.image[0]" :alt="product.name" class="prod-img" />
		<figcaption>
			<h4>More</h4>
			<p class="prod-name">{{ product.name }}</p>
			<p class="prod-desc">{{ product.description.slice(0, 100) }}...</p>
			<div class="rating-wrapper">
				<p class="rating">
					{{
						product.aggregateRating?.ratingValue.toFixed(1) ||
						'Not yet reviewed'
					}}
					<span v-if="product.aggregateRating?.ratingValue"
						>&starf;</span
					>
				</p>
				<p class="price">${{ product.offers.highPrice }}</p>
			</div>
			<a :href="product.path" class="view-link"
				>View &blacktriangleright;</a
			>
		</figcaption>
	</figure>
</template>

<style scoped>
.zoom-card {
	position: relative;
	width: 100%;
	max-width: 300px;
	height: 450px;
	margin: 0 auto 2rem;
	box-shadow: 0 1px 3px rgba(0, 0, 0, 0.15), 0 1px 2px rgba(0, 0, 0, 0.3);
	transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
	overflow: hidden;
}
.zoom-card:hover,
.zoom-card.hovered {
	box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3), 0 10px 10px rgba(0, 0, 0, 0.27);
}
.zoom-card:hover img,
.zoom-card.hovered img {
	transform: scale(1.15);
}
.zoom-card:hover .prod-brand,
.zoom-card.hovered .prod-brand {
	opacity: 0;
	transform: scale(0.65);
}
.zoom-card:hover figcaption,
.zoom-card.hovered figcaption {
	bottom: 0;
}
.prod-brand {
	position: absolute;
	top: 10px;
	left: 10px;
	margin: 0;
	padding: 0;
	color: #fff;
	font-size: 1.5rem;
	line-height: 1;
	opacity: 1;
	transform: scale(1);
	transition: 0.3s ease;
	z-index: 10;
}
.prod-img {
	width: 100%;
	height: auto;
	transition: 0.25s;
}
figcaption {
	position: absolute;
	bottom: -34%;
	left: 0;
	width: 100%;
	margin: 0;
	padding: 1rem;
	color: #fff;
	font-size: 1rem;
	line-height: 1;
	background: rgba(0, 0, 0, 0.85);
	box-shadow: 0 0 20px rgba(0, 0, 0, 0.4);
	transition: 0.25s;
}
figcaption h4 {
	padding: 0;
	margin: 0 0 1rem;
}
figcaption .prod-name {
	margin-bottom: 0.5rem;
}
figcaption .prod-desc {
	font-size: 0.875rem;
	line-height: 1.2;
	margin-bottom: 0.5rem;
}
figcaption .rating-wrapper {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 0.5rem;
}
figcaption .view-link {
	text-decoration: none;
	color: rgb(240, 204, 0);
	display: block;
	width: fit-content;
	margin: 0 auto;
}
</style>
