<script setup>
import { ref, computed } from 'vue';

const props = defineProps({
	product: { type: Object, required: false },
	index: { type: Number, required: false },
});

const isFlipped = ref(false);
const activeHotspot = ref(1);

function toggleFlipped() {
	isFlipped.value = !isFlipped.value;
}

function updateHotspot(hotspot) {
	activeHotspot.value = hotspot;
}

function handleClick(hotspot) {
	toggleFlipped();
	updateHotspot(hotspot);
}
</script>

<template>
	<div class="flip-card" :class="{ flipped: isFlipped }">
		<div class="card-face card-front">
			<img :src="product.image[0]" :alt="product.name" />

			<div
				class="hotspot hs1"
				@click="handleClick(1)"
				:style="product.associatedProducts.products[0].hotspot.style"
			></div>
			<div
				class="hotspot hs2"
				@click="handleClick(2)"
				:style="product.associatedProducts.products[1].hotspot.style"
			></div>
			<div
				class="hotspot hs3"
				@click="handleClick(3)"
				:style="product.associatedProducts.products[2].hotspot.style"
			></div>
		</div>

		<div class="card-face card-back">
			<div
				v-for="(prod, i) in product.associatedProducts.products"
				:key="i"
				class="hs-prod"
			>
				<div v-if="activeHotspot === prod.hotspot.id">
					<div class="card-back-header">
						<span>{{ prod.name }}</span>
						<button
							type="button"
							class="close-btn"
							@click="toggleFlipped"
						>
							&times;
						</button>
					</div>
					<a :href="prod.path" class="prod-img-link">
						<img :src="prod.image[0]" :alt="prod.name" />
					</a>
					<p class="prod-desc">
						{{ prod.description.slice(0, 75) }}...
					</p>
					<div class="price-wrap">
						<span class="price">${{ prod.offers.highPrice }}</span>
						<a :href="prod.path">View &blacktriangleright;</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped>
@keyframes pulsate {
	0% {
		opacity: 0;
	}
	50% {
		opacity: 1;
	}
	100% {
		opacity: 0;
	}
}
.flip-card {
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
.card-back .prod-img-link {
	display: block;
	width: 65%;
	height: 50%;
	margin: 0 auto 1rem;
}
.card-front img {
	width: 100%;
	height: auto;
}
.card-back {
	background: #ececec;
	padding: 0.75rem;
	transform: rotateY(180deg);
}
.flip-card.flipped .card-front {
	transform: rotateY(-180deg);
}
.flip-card.flipped .card-back {
	transform: rotateY(0);
}
.card-back-header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 1rem;
}
.card-back .close-btn {
	border: 0;
	background: transparent;
	font-size: 1.75rem;
	color: #777;
	cursor: pointer;
}
.card-back .prod-img-link img {
	width: 100%;
	height: auto;
}
.card-back .prod-desc,
.card-back .price-wrap a {
	font-size: 0.875rem;
	line-height: 1.2;
}
.card-back .prod-desc {
	margin-bottom: 0.5rem;
}
.card-back .price-wrap a {
	text-decoration: none;
}
.card-back .price-wrap {
	display: flex;
	justify-content: space-between;
	align-items: center;
}
.hotspot {
	border: 1px solid silver;
	width: 50px;
	height: 50px;
	border-radius: 100%;
	position: absolute;
	cursor: pointer;
	animation: pulsate ease-in-out 6000ms infinite;
}
.hotspot:hover {
	border: 1px solid #ed7513;
	animation: none;
}
</style>
