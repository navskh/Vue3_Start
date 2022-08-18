<template>
	<div>
		<h2>반응형 메세지</h2>
		<p>{{ reactiveMesage }}</p>
		<button v-on:click="addReacitveMessage">Add Message</button>
		<h2>일반 메세지</h2>
		<p>{{ normalMessage }}</p>
		<button v-on:click="addNormalMessage">Add Message</button>
	</div>
</template>

<script>
import { isRef, ref } from 'vue';
export default {
	setup() {
		const reactiveMesage = ref('Hello Reactive Message');
		const addReacitveMessage = () => {
			reactiveMesage.value = reactiveMesage.value + '!';
		};

		console.log(isRef(reactiveMesage));

		let normalMessage = 'Hello Normal Message';
		const addNormalMessage = () => {
			normalMessage = normalMessage + ':';
		};
		console.log(isRef(normalMessage));

		return {
			reactiveMesage,
			normalMessage,
			addReacitveMessage,
			addNormalMessage,
		};
	},
};
</script>

<style></style>
