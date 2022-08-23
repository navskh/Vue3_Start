<template>
	<div class="container py-4">
		<div class="card">
			<div class="card-header">Provide Inject Component</div>
			<div class="card-body">
				<Child></Child>
				<p>{{ appMessage }}</p>
			</div>
		</div>
	</div>
</template>

<script>
import { inject, provide, readonly, ref } from 'vue';
import Child from './Child.vue';
export default {
	components: {
		Child,
	},
	setup() {
		const staticMessage = 'static message';
		const count = ref(10);
		const message = ref('message');
		const updateMessage = () => {
			message.value = message.value + '!';
		};
		provide('message', { message: readonly(message), updateMessage });
		provide('static-message', staticMessage);
		provide('count', count);

		const appMessage = inject('app-message');
		return { appMessage };
	},
};
</script>

<style lang="scss" scoped></style>
