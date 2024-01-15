<template>
	<div class="flex gap-x-2 justify-center">
		<template v-for="i in rate" :key="`testimonial-rating-${key}`">
			<span class="text-yellow-500 text-3xl">&#9733;</span>
		</template>
		<template v-if="rate == 5">
			<template v-for="i in 5 - rate" :key="`testimonial-rating-${key}`">
				<span>&#9734; </span>
			</template>
		</template>
	</div>
</template>

<script setup lang="ts">
	defineProps({
		rate: Number,
		key: String,
	});
</script>
