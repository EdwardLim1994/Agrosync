<template>
	<div>
		<h1
			transition:name="strategies-title"
			class="text-4xl font-bold text-white text-center uppercase mb-12"
		>
			Our Solutions in Action
		</h1>

		<div class="h-[30rem] flex items-center">
			<Carousel
				:autoplay="2000"
				:breakpoints="breakpoints"
				:transition="500"
				:wrap-around="true"
			>
				<Slide
					v-for="(slide, index) in info"
					:key="`testimonial-carousel-slide-${index}`"
					class="p-6 rounded-lg backdrop-blur-lg bg-gray-700/70"
				>
					<div class="carousel__item p-6">
						<Rating :rate="slide.rate" />
						<p class="text-white text-lg">{{ slide.comment }}</p>
						<h3 class="text-white mt-8 font-bold italic text-2xl">
							{{ slide.name }}
						</h3>
					</div>
				</Slide>
			</Carousel>
		</div>
	</div>
</template>
<script setup lang="ts">
	import { Carousel, Slide } from "vue3-carousel";

	import "vue3-carousel/dist/carousel.css";

	import Rating from "../Rating.vue";
	import { readonly } from "vue";

	const breakpoints = {
		700: {
			itemsToShow: 1.95,
		},
		// 1024 and up
		1240: {
			itemsToShow: 3.95,
		},
	};

	const info = readonly([
		{
			rate: 5,
			name: "John Smith",
			comment:
				"Incredible! Agrosync has transformed the way I approach farming. The AI insights are a game-changer, making every decision smarter and more efficient.",
		},
		{
			rate: 5,
			name: "Emily Chen",
			comment:
				"As a farmer, time is everything. Thanks to Agrosync's automation solutions, I've saved valuable hours, allowing me to focus on what truly matters - the crops",
		},
		{
			rate: 5,
			name: "Carlos Rodriguez",
			comment:
				"Agrosync doesn't just provide solutions; they provide peace of mind. Predictive analytics helped me navigate weather uncertainties, safeguarding my crops and investments.",
		},
		{
			rate: 5,
			name: "Samuel Lee",
			comment:
				"Sustainability matters. Agrosync not only delivers cutting-edge tech but does it with a commitment to sustainable practices. Proud to be a part of this agricultural revolution!",
		},
		{
			rate: 5,
			name: "Megan Turner",
			comment:
				"The precision agriculture tools from Agrosync have significantly increased my farm's productivity. It's like having a digital assistant for my crops - efficient and effective!",
		},
	]);
</script>

<style global>
	.carousel__viewport {
		height: 25rem !important;
		display: flex;
		align-items: center;
		width: 100%;
	}

	.carousel__track {
		height: 25rem !important;
		width: 100%;
	}

	.carousel {
		height: 25rem !important;
		display: flex;
		align-items: center;
		width: 100%;
	}
</style>

<style scoped>
	.carousel__viewport {
		perspective: 2000px;
	}

	.carousel__track {
		transform-style: preserve-3d;
	}

	.carousel__slide--sliding {
		transition: 0.5s;
	}

	.carousel__slide {
		opacity: 0.9;
		transform: rotateY(-20deg) scale(0.9);
	}

	.carousel__slide--active ~ .carousel__slide {
		transform: rotateY(20deg) scale(0.9);
	}

	.carousel__slide--prev {
		opacity: 1;
		transform: rotateY(-10deg) scale(0.95) translateX(-15px);
	}

	.carousel__slide--next {
		opacity: 1;
		transform: rotateY(10deg) scale(0.95);
	}

	.carousel__slide--active {
		opacity: 1;
		transform: rotateY(0) scale(1.1);
	}
</style>
