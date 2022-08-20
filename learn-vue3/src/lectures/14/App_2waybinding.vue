<template>
	<div>
		<h2>input value</h2>
		<input type="text" v-model="inputValue" />
		<div>{{ inputValue }}</div>

		<h2>textarea</h2>
		<textarea v-model="textareaValue"></textarea>
		<div>{{ textareaValue }}</div>

		<h2>checkbox</h2>
		<label for="checkbox"> {{ checkboxValue }}</label>
		<input id="checkbox" type="checkbox" v-model="checkboxValue" />

		<h2>radio</h2>
		<label>
			<input type="radio" name="text" value="O" v-model="radioValue" /> O형
		</label>
		<label>
			<input type="radio" name="text" value="A" v-model="radioValue" /> A형
		</label>
		<label>
			<input type="radio" name="text" value="AB" v-model="radioValue" /> AB형
		</label>

		<div>
			{{ radioValue }}
		</div>

		<h2>select</h2>
		<select v-model="selectValue">
			<option value="html">html</option>
			<option value="javascript">javascript</option>
			<option value="vue">vue</option>
		</select>
		<div>{{ selectValue }}</div>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const inputValue = ref(null);
		const textareaValue = ref(null);
		const checkboxValue = ref(true);
		const radioValue = ref('O');
		const selectValue = ref('html');
		return {
			inputValue,
			textareaValue,
			checkboxValue,
			radioValue,
			selectValue,
		};
	},
};
</script>

<style></style>
