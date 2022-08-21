<template>
	<div>
		<label
			>{{ label }}
			<input v-model="value" type="text" />
			<!-- v-model="modelValue"
				@input="event => $emit('update:modelValue', event.target.value)" -->
		</label>
	</div>
</template>

<script>
import { computed } from 'vue';
export default {
	props: ['modelValue', 'label'],
	emits: ['update:modelValue'],
	setup(props, { emit }) {
		const value = computed({
			get() {
				console.log(props.modelValue);
				return props.modelValue;
			},
			set(value) {
				emit('update:modelValue', value);
			},
		});
		return { value };
	},
};
</script>

<style lang="scss" scoped></style>
