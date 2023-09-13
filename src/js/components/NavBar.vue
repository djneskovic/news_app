<template>
	<main id="navbar">
		<div class="container">
			<div class="navbar flex justify-between items-center p-4">
				<div class="logo">
					<img src="../../../public/images/logo.png" alt="" />
				</div>

				<div class="search">
					<input
						type="text"
						placeholder="e.g. Sport"
						v-model="search"
					/>
					<button @click="filterNews">Search</button>
				</div>
			</div>
		</div>
	</main>
</template>

<script setup>
import { ref } from "vue";

const search = ref("");

function filterNews() {
	console.log(search.value);
	search.value = "";
}
</script>
