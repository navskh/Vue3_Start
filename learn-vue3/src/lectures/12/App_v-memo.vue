<template>
	<div>
		<div v-memo="[subscribe]">
			<p>subscribe : {{ subscribe }}</p>
			<p>views : {{ views }}</p>
			<p>likes : {{ likes }}</p>
			<button @click="subscribe++">subscribe</button>
			<button @click="views++">views</button>
			<button @click="likes++">likes</button>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const subscribe = ref(4000);
		const views = ref(4000);
		const likes = ref(20);

		return {
			subscribe,
			views,
			likes,
		};
	},
};
</script>

<style></style>
