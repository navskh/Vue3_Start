<template>
	<div>
		<p>{{ msg }}</p>
		<p v-text="msg"></p>
		<p v-html="htmlstr"></p>

		<p>{{ msg }} !!!</p>
		<p v-once>{{ msg }} !!!</p>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const msg = ref('안녕하세요');
		const htmlstr = ref('<strong>안녕!!</strong>');
		return {
			msg,
			htmlstr,
		};
	},
};
</script>

<style></style>
;
