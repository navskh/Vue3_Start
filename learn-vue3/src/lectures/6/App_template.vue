<template>
	<div>
		<h2>보간법</h2>
		<p v-once>{{ message }}</p>
		<p>{{ message }}</p>
		<button v-on:click="message = message + '!'">버튼</button>
		<hr />
		<h2>v-html</h2>
		<p>{{ rawHtml }}</p>
		<p v-html="rawHtml"></p>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('안녕하세요');
		const rawHtml = ref('<strong>안녕하세!</strong>');

		return {
			message,
			rawHtml,
		};
	},
};
</script>

<style></style>
