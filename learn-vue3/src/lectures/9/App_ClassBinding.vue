<template>
	<div>
		<div :class="classObject">텍스트 입니다.</div>
		<button v-on:click="toggle">toggle</button>
	</div>
</template>

<script>
import { ref, reactive, computed } from 'vue';
export default {
	setup() {
		const isActive = ref(true);

		const toggle = () => {
			isActive.value = !isActive.value;
		};

		// const classObject = reactive({
		// 	active: true,
		// 	'text-danger': true,
		// });

		const classObject = computed(() => {
			return {
				active: true,
				'text-danger': true,
			};
		});

		return { isActive, toggle, classObject };
	},
};
</script>

<style>
.active {
	font-weight: 900;
}
</style>
