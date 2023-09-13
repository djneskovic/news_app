<template>
	<div class="newsItem">
		<img :src="srcToImg" alt="" />
		<h2>{{ title }}</h2>
		<p class="italic mb-4">{{ description }}</p>
		<a :href="srcToLink">Check News</a>
	</div>
</template>

<script>
export default {
	props: ["srcToImg", "title", "description", "srcToLink"],
};
</script>
