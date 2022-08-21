<template>
	<div>
		<theNavVue></theNavVue>
		<theViewVue></theViewVue>
	</div>
</template>

<script>
import theNavVue from './components/theNav.vue';
import theViewVue from './components/theView.vue';

export default {
	components: {
		theNavVue,
		theViewVue,
	},
	setup() {
		return {};
	},
};
</script>

<style>
#app {
	display: block !important;
}
</style>
