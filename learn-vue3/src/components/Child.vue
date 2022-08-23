<!-- eslint-disable vue/multi-word-component-names -->
<template>
	<div class="card">
		<div class="card-header">Child Component</div>
		<div class="card-body">
			<DeepChildVue></DeepChildVue>
		</div>
	</div>
</template>

<script>
import DeepChildVue from './DeepChild.vue';
export default {
	components: {
		DeepChildVue,
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
