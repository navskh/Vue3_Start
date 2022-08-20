<template>
	<div></div>
</template>

<script>
import { reactive, ref, watch } from 'vue';
export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		const obj = reactive({
			count: 0,
		});

		watch(obj, (newValue, oldValue) => {
			console.log(newValue, oldValue);
		});
		// watch(() => {
		// 	x.value + y.value,
		// 		sum => {
		// 			console.log('sum : ', sum);
		// 		};
		// });

		// watch([x, y], ([newX, newY]) => {
		// 	console.log(newX, newY);
		// });
		return { x, y, obj };
	},
};
</script>

<style lang="scss" scoped></style>
