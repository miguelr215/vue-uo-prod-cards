<script setup>
import { onMounted } from 'vue';
import UOHeader from '@/components/UOHeader.vue';
import FlipCard from '@/components/FlipCard.vue';
import ProductsShowcase from '@/components/ProductsShowcase.vue';
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

		<FlipCard />

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
