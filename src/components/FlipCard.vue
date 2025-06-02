<script setup>
import { ref } from 'vue';

const isFlipped = ref(false);

function toggleFlipped() {
	console.log('before:', isFlipped.value);
	isFlipped.value = !isFlipped.value;
	console.log('after:', isFlipped.value);
}
</script>

<template>
	<section>
		<h2>Flip Card</h2>

		<div class="flip-container">
			<div class="flip-card" :class="{ flipped: isFlipped }">
				<div class="card-face card-front">
					<picture
						class="o-pwa-image has-pwa-aspect-ratio is-loaded"
						viewcode="b"
						alt="BDG Eva Tie-Front Ruched Strap Trapeze Mini Dress"
						disabled="false"
						baseurl="https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b"
						url="https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=640"
						urlthumbnail="https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=100"
						urlhighres="https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$redesign-zoom-5x$"
						isvideo="false"
						index="0"
						><source
							srcset="
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=1314 1314w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=1080 1080w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=960   960w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=720   720w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=640   640w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=540   540w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;fmt=webp&amp;qlt=80&amp;wid=360   360w
							"
							sizes="(min-width: 768px) 40vw, calc(100vw - 40px)"
							type="image/webp" />
						<img
							class="o-pwa-image__img"
							width="200"
							height="300"
							srcset="
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=1314 1314w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=1080 1080w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=960   960w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=720   720w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=640   640w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=540   540w,
								https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=360   360w
							"
							sizes="(min-width: 768px) 40vw, calc(100vw - 40px)"
							src="https://images.urbndata.com/is/image/UrbanOutfitters/99180069_049_b?$xlarge$&amp;fit=constrain&amp;qlt=80&amp;wid=640"
							alt="BDG Eva Tie-Front Ruched Strap Trapeze Mini Dress"
							fetchpriority="auto"
					/></picture>

					<div class="hotspot hs1" @click="toggleFlipped"></div>
					<div class="hotspot hs2" @click="toggleFlipped"></div>
					<div class="hotspot hs3" @click="toggleFlipped"></div>

					<div class="line hs1-line1"></div>
					<div class="line hs1-line2"></div>
					<div class="line hs2-line1"></div>
					<div class="line hs2-line2"></div>
					<div class="line hs3-line1"></div>
					<div class="line hs3-line2"></div>
				</div>

				<div class="card-face card-back">
					<button type="button" @click="toggleFlipped">close</button>
				</div>
			</div>
		</div>
	</section>
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
section {
	margin: 2rem 0;
	perspective: 600px;
}
.flip-card {
	position: relative;
	width: 100%;
	max-width: 300px;
	min-height: 450px;
	margin: 0 auto;
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
	box-shadow: 0 2rem 4rem rgba(#000, 0.15);
	transition: all 0.8s ease;
}
.card-front img {
	width: 100%;
	height: auto;
}
.card-back {
	background: purple;
	transform: rotateY(180deg);
}
.flip-card.flipped .card-front {
	transform: rotateY(-180deg);
}
.flip-card.flipped .card-back {
	transform: rotateY(0);
}
.hotspot {
	border: 1px solid silver;
	width: 50px;
	height: 50px;
	border-radius: 100%;
	position: absolute;
	cursor: pointer;
	animation: pulsate ease-in-out 7000ms infinite;
}
.hotspot:hover {
	border: 1px solid gold;
	animation: none;
}
.hs1 {
	top: 180px;
	left: 38%;
	width: 85px;
	height: 85px;
}
.hs2 {
	top: 130px;
	left: 90px;
}
.hs3 {
	bottom: 15px;
	left: 35%;
	width: 120px;
	height: 25px;
	border-radius: 0;
}
@media (min-width: 768px) {
	section {
		margin: 3rem 0;
	}
}
</style>
