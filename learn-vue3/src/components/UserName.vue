<template>
	<div>
		<LabelInputVue
			:model-value="firstname"
			@update:model-value="value => $emit('update:firstname', value)"
			label="성"
		></LabelInputVue>
		<LabelInputVue
			:model-value="lastname"
			@update:model-value="value => $emit('update:lastname', value)"
			label="이름"
		></LabelInputVue>
	</div>
</template>

<script>
import LabelInputVue from './LabelInput.vue';

export default {
	props: ['firstname, lastname'],
	emits: ['update:firstname, update:lastname'],
	components: {
		LabelInputVue,
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
