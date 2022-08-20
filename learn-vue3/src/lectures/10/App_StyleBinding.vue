<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio aspernatur
			quod quibusdam minima, ut atque, dolor consequatur porro voluptatem quidem
			voluptate dicta ab numquam ex ipsa quisquam illum reprehenderit facilis?
		</div>
		<button v-on:click="fontSize++">+</button>
		<button v-on:click="fontSize--">-</button>
	</div>
</template>

<script>
import { ref, reactive, computed } from 'vue';
export default {
	setup() {
		const fontSize = ref(13);
		const styleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontSize.value + 'px',
			};
		});

		return { styleObject, fontSize };
	},
};
</script>

<style></style>
