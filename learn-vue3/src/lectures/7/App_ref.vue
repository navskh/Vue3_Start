<template>
	<div>
		<p>{{ message }}</p>
		<button @click="increment">dd</button>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('Hello Vue');
		const increment = () => {
			message.value = message.value + '!0';
		};

		return {
			message,
			increment,
		};
	},
};
</script>

<style></style>
