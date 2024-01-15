<template>
	<h1 class="text-4xl font-bold uppercase">Contact Us</h1>
	<h3 class="text-xl font-semibold my-4">
		Let's Cultivate the Future Together!
	</h3>
	<form
		@submit.prevent="submit"
		class="flex flex-col w-full lg:w-1/2 bg-gray-600/50 backdrop-blur-lg p-8 rounded-lg gap-y-6 mt-7"
	>
		<div class="flex flex-col gap-y-4">
			<label
				class="text-white text-lg font-semibold"
				for="contact-us-name"
			>
				Your Name
			</label>
			<input
				class="rounded p-2 px-5"
				type="text"
				name="name"
				id="contatc-us-name"
			/>
		</div>
		<div class="flex flex-col gap-y-4">
			<label
				class="text-white text-lg font-semibold"
				for="contact-us-email"
			>
				Your Email
			</label>
			<input
				class="rounded p-2 px-5"
				type="email"
				name="email"
				id="contatc-us-email"
			/>
		</div>
		<div class="flex flex-col gap-y-4">
			<label
				class="text-white text-lg font-semibold"
				for="contact-us-category"
			>
				Category
			</label>
			<select
				class="rounded p-2 px-5"
				name="category"
				id="contact-us-category"
			>
				<option disabled>Select</option>
				<option>Question</option>
				<option>Report Bugs</option>
				<option>Support</option>
				<option>Other</option>
			</select>
		</div>
		<div class="flex flex-col gap-y-4">
			<label
				class="text-white text-lg font-semibold"
				for="contact-us-content"
			>
				Content
			</label>
			<textarea
				class="rounded p-2 px-5"
				name="content"
				id="contact-us-content"
				rows="8"
			/>
		</div>
		<button
			class="text-white bg-green-500 hover:bg-green-800 active:bg-green-300 rounded-lg w-full py-4 text-xl font-semibold"
		>
			Submit
		</button>
	</form>
</template>

<script setup lang="ts">
	function submit() {
		console.log("Submitted");
	}
</script>
