<template>
	<particles
		:style="{
			position: 'absolute !important',
			top: 0,
			left: 0,
			bottom: 0,
			right: 0,
			padding: 0,
			margin: 0,
			'z-index': '-20 !important',
		}"
		:id="id ?? ''"
		:particlesInit="async (engine: any) => {
		await loadSlim(engine);
	}"
		:options="{ fullScreen: { enable: false }, ...options }"
	/>
</template>

<script setup lang="ts">
	import { loadSlim } from "tsparticles-slim";
	defineProps({
		options: Object,
		id: String,
	});
</script>
