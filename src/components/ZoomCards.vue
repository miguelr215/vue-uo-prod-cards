<script setup>
import ZoomCard from '@/components/ZoomCard.vue';

const props = defineProps({
	products: { type: Array, required: false },
});
</script>

<template>
	<section>
		<h2>Zoom Hover Cards</h2>

		<div class="zoom-container" v-if="products.length">
			<ZoomCard
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
	.zoom-container {
		margin: 3rem 0;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
}
</style>
