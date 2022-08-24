<template>
	<div class="container py-4"></div>
</template>

<script>
export default {
	setup() {
		console.log('setup');
		return {};
	},
	beforeCreate() {
		console.log('beforeCreated');
	},
	created() {
		console.log('Created');
	},
};
</script>

<style lang="scss" scoped></style>
