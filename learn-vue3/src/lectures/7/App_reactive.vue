<template>
	<div>
		<button v-on:click="state.count++">Click {{ state.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';
export default {
	setup() {
		const state = reactive({
			count: 0,
		});

		return {
			state,
		};
	},
};
</script>

<style></style>
