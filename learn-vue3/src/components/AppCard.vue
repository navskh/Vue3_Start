<template>
	<div>
		<div class="card">
			<div class="card-body">
				<!-- type : nes, notice -->
				<span class="badge bg-secondary">{{ typeName }}</span>
				<h5 class="card-title mt-2">{{ title }}</h5>
				<p class="card-text">
					{{ contents }}
				</p>
				<a href="#" :class="isLikeClass" @click="toggleLike">좋아요</a>
			</div>
		</div>
	</div>
</template>

<script>
import { computed } from 'vue';
export default {
	props: {
		type: {
			type: String,
			default: 'news',
			validator: value => {
				return ['news', 'notice'].includes(value);
			},
		},
		title: {
			type: String,
			required: true,
		},
		contents: {
			type: String,
			// required: true,
		},
		isLike: {
			type: Boolean,
			default: false,
		},
	},
	emits: ['toggleLike'],
	setup(props, context) {
		const isLikeClass = computed(() =>
			props.isLike ? 'btn btn-danger' : 'btn btn-outline-danger',
		);

		const typeName = computed(() =>
			props.type === 'news' ? '뉴스' : '공지사항',
		);

		const toggleLike = () => {
			context.emit('toggleLike');
		};
		return { isLikeClass, typeName, toggleLike };
	},
};
</script>

<style lang="scss" scoped></style>
