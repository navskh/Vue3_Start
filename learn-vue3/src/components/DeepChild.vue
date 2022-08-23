<template>
	<div class="card">
		<div class="card-header">Deep Child Component</div>
		<div class="card-body">
			<p>{{ staticMessage }}</p>
			<p>{{ message }}</p>
			<p>{{ count }}</p>
		</div>
	</div>
</template>

<script>
import { inject } from 'vue';
export default {
	setup() {
		const staticMessage = inject('static-message');
		const { message, updateMessage } = inject('message');
		// message.value = message.value + '!';
		// 이렇게하지말고, provider에서 업데이트 함수 제공하라!
		updateMessage();
		const count = inject('count');

		return { staticMessage, message, count };
	},
};
</script>

<style lang="scss" scoped></style>
