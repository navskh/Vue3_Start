<template>
	<div></div>
</template>

<script>
import { reactive, ref } from 'vue';
export default {
	setup() {
		const original = reactive({
			count: 0,
		});

		original.count++;

		console.log(original.count++);
	},
};
</script>

<style></style>
