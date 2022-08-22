<template>
	<div>
		<main>
			<div class="container py-4">
				<MyButton @click="sayHello"></MyButton>
				<LabelInput></LabelInput>

				<hr />
				<FancyButton>Click!</FancyButton>
				<AppCardVue>
					<!-- <template #[slotArgs]> 제목입니다. </template> -->
					<template #default="{ childMessage }">
						{{ childMessage }}
					</template>
				</AppCardVue>
				<hr />
				<AppCardVue>게시글입니다.</AppCardVue>
			</div>
		</main>
	</div>
</template>

<script>
import { reactive, ref } from 'vue';
import MyButton from './MyButton.vue';
import LabelInput from './LabelInput.vue';
import FancyButton from './FancyButton.vue';
import PostItem from './PostItem.vue';
import AppCardVue from './AppCard.vue';

export default {
	components: {
		MyButton,
		LabelInput,
		FancyButton,
		AppCardVue,
	},
	setup() {
		const sayHello = () => {
			alert('안녕하세요');
		};

		const slotArgs = ref('header');
		return { sayHello, slotArgs };
	},
};
</script>

<style lang="scss" scoped></style>
