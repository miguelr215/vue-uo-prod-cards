<script setup>
import { onMounted, ref } from 'vue';
import SkipToContent from './components/SkipToContent.vue';
import UOHeader from '@/components/UOHeader.vue';
import HoverFlipCards from '@/components/HoverFlipCards.vue';
import FlipCards from '@/components/FlipCards.vue';
import ZoomCards from '@/components/ZoomCards.vue';

const products = ref([]);

onMounted(() => {
	async function getProducts() {
		try {
			const res = await fetch('products.json');
			const data = await res.json();
			products.value = data;
		} catch (error) {
			console.log(`error: ${error}`);
		}
	}

	getProducts();
});
</script>

<template>
	<!-- <SkipToContent /> -->
	<UOHeader />
	<main id="content">
		<h1>Product Card Animations</h1>
		<ul>
			<li>Developed with Vue 3 &amp; Vite</li>
			<li>Flexible &amp; Reusable components</li>
			<li>Accessible and Mobile Responsive</li>
		</ul>

		<HoverFlipCards :products="products" />

		<FlipCards :products="products" />

		<ZoomCards :products="products" />
	</main>
</template>

<style scoped>
main {
	padding: 1rem 1rem 2rem;
}
main h1 {
	text-align: center;
}
main ul {
	width: fit-content;
	margin: 1rem auto;
}
@media (min-width: 768px) {
	main ul {
		width: 35%;
	}
}
@media (min-width: 992px) {
	main {
		padding-bottom: 3rem;
	}
	main ul {
		width: 100%;
		display: flex;
		justify-content: center;
		gap: 3rem;
	}
}
</style>
