<script setup>
import { onMounted, ref } from 'vue';
import UOHeader from '@/components/UOHeader.vue';
import FlipCards from '@/components/FlipCards.vue';
import ProductsShowcase from '@/components/ProductsShowcase.vue';

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
	<UOHeader />
	<main>
		<h1>Flip Card & Products Showcase</h1>
		<ul>
			<li>Developed with Vue &amp; Vite</li>
			<li>3 clickable "hot spots" show product details from image</li>
			<li>Reusable component</li>
			<li>Accessible and Responsive</li>
		</ul>

		<FlipCards :products="products" />

		<!-- <ProductsShowcase /> -->
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
	width: 60%;
	margin: 1rem auto;
}
@media (min-width: 768px) {
	main ul {
		width: 35%;
	}
}
@media (min-width: 992px) {
	main ul {
		width: 100%;
		display: flex;
		justify-content: space-between;
		gap: 1rem;
	}
	main li {
		max-width: 23%;
	}
}
</style>
