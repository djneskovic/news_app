<template>
	<main id="newsFeed">
		<div class="container">
			<div class="newsFeed mt-8 gap-8">
				<NewsItem
					v-for="item in newsData"
					:key="item.title"
					:srcToImg="item.urlToImage"
					:title="item.title"
					:description="item.description"
					:srcToLink="item.url"
				/>
			</div>
		</div>
	</main>
</template>

<script setup>
import NewsItem from "./NewsItem.vue";
import axios from "axios";
import { ref, onMounted } from "vue";

const newsData = ref([]);

function getNews() {
	axios(
		"https://newsapi.org/v2/everything?domains=bbc.co.uk&apiKey=395f7e47fafd4b97958755892f74e9c5"
	)
		.then((res) => {
			const data = res.data.articles;
			console.log(data);
			newsData.value = data;
		})
		.catch((err) => {
			console.log(err);
		});
}

onMounted(() => {
	getNews();
});
</script>

<style scoped>
.newsFeed {
	display: grid;
	place-items: center;
	grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
}
</style>
