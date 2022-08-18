<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p> -->
		<p>{{ hasLecture }}</p>
		<p>{{ existLecture() }}</p>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { reactive, computed, ref } from 'vue';
export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', 'Javascript', 'VUe3'],
		});

		const hasLecture = computed(() =>
			teacher.lectures.length > 0 ? '있음' : '없음',
		);

		const existLecture = () => (teacher.lectures.length > 0 ? '있음' : '없음');

		const firstName = ref('홍');
		const lastName = ref('길동');
		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});

		fullName.value = '짐 코딩';

		return {
			teacher,
			hasLecture,
			existLecture,
			fullName,
		};
	},
};
</script>

<style></style>
