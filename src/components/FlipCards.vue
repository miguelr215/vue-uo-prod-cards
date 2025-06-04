<script setup>
import FlipCard from '@/components/FlipCard.vue';

const props = defineProps({
	products: { type: Array, required: false },
});
</script>

<template>
	<section>
		<h2>Hotspot Flip Cards</h2>
		<p class="subtitle">Click a hotspot to reveal product details</p>

		<div class="flip-container" v-if="products.length">
			<FlipCard
				v-for="(product, index) in products"
				:key="index"
				:product="product"
				:index="index"
			/>
		</div>
	</section>
</template>

<style scoped>
section {
	margin: 2rem 0;
}
h2,
.subtitle {
	text-align: center;
}
@media (min-width: 992px) {
	h2,
	.subtitle {
		text-align: left;
	}
	.flip-container {
		margin: 3rem 0;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
}
</style>
