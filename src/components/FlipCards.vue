<script setup>
import FlipCard from '@/components/FlipCard.vue';

const props = defineProps({
	products: { type: Array, required: false },
});
</script>

<template>
	<section>
		<h2>Flip Cards</h2>

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
@media (min-width: 992px) {
	.flip-container {
		margin: 3rem 0;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
}
</style>
