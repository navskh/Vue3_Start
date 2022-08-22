<template>
	<div>
		<div class="card">
			<div v-if="$slots.header" class="card-header">
				<slot name="header"></slot>
			</div>
			<div class="card-body">
				<slot :child-message="childMessage" hello-message="안녕하세요"
					>#body</slot
				>
			</div>
			<div v-if="$slots.header" class="card-footer text-muted">
				<slot name="footer"></slot>
			</div>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const childMessage = ref('자식컴포넌트 메시지');
		return { childMessage };
	},
};
</script>

<style lang="scss" scoped></style>
