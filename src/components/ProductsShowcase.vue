<script setup>
import { ref } from 'vue';

const isFlipped = ref(false);
</script>

<template>
	<section class="showcase">
		<h2>Prod name</h2>
		<div class="prod-img-wrapper" :class="{ flipped: isFlipped }">
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

			<div class="hotspot hs1"></div>
			<div class="hotspot hs2"></div>
			<div class="hotspot hs3"></div>

			<div class="line hs1-line1"></div>
			<div class="line hs1-line2"></div>
			<div class="line hs2-line1"></div>
			<div class="line hs2-line2"></div>
			<div class="line hs3-line1"></div>
			<div class="line hs3-line2"></div>
		</div>
	</section>
</template>

<style scoped>
.card-back {
	background-color: purple;
}
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
.showcase {
	margin: 2rem 0;
}
.prod-img-wrapper {
	position: relative;
	width: 100%;
	max-width: 300px;
	margin: 0 auto;
}
.prod-img-wrapper img {
	width: 100%;
	height: auto;
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
	top: 150px;
	left: 40%;
	width: 75px;
	height: 75px;
}
.hs2 {
	top: 105px;
	left: 65px;
}
.hs3 {
	bottom: 15px;
	left: 35%;
	width: 100px;
	height: 25px;
	border-radius: 0;
}
</style>
