<script setup>
import HoverFlipCard from '@/components/HoverFlipCard.vue';

const props = defineProps({
	products: { type: Array, required: false },
});
</script>

<template>
	<section>
		<h2>Hover Flip Cards</h2>

		<div class="hover-flip-container" v-if="products.length">
			<HoverFlipCard
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
h2 {
	text-align: center;
}
@media (min-width: 992px) {
	h2 {
		text-align: left;
	}
	.hover-flip-container {
		margin: 3rem 0;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
}
</style>
