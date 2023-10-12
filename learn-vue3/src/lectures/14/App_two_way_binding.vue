<template>
	<div>
		<h2>input value</h2>
		<!-- <input type="text" v-model.lazy="inputValue" /> -->
		<!-- <input type="text" v-model.number="inputValue" /> -->
		<input type="text" v-model.trim="inputValue" />
		<!-- :value="inputValue"
			@input="event => (inputValue = event.target.value)" -->
		<div>{{ inputValue }}</div>
		<div>{{ typeof inputValue }}</div>
		<hr />
		<h2>textarea value</h2>
		<textarea v-model="textareaValue"></textarea>
		<!-- :value="inputValue"
			@input="event => (textareaValue = event.target.value)" -->
		<div>{{ textareaValue }}</div>
		<hr />
		<h2>checkbox value</h2>
		<label for="checkbox">{{ checkboxValue }}</label>
		<input
			type="checkbox"
			id="checkbox"
			v-model="checkboxValue"
			true-value="Yes"
			false-value="No"
		/>
		<hr />
		<h2>checkbox values</h2>
		<label>
			<input type="checkbox" value="html" v-model="checkboxValues" />
			HTML
		</label>
		<label>
			<input type="checkbox" value="css" v-model="checkboxValues" />
			CSS
		</label>
		<label>
			<input type="checkbox" value="javascript" v-model="checkboxValues" />
			JavaScript
		</label>
		<div>{{ checkboxValues }}</div>
		<!-- :checked="checkboxValue"
			@change="event => (checkboxValue = event.target.checked)" -->
		<hr />
		<h2>radio value</h2>
		<label>
			<input type="radio" name="type" value="A" v-model="radioValue" />
			<!-- :checked="radioValue === 'A'"
				@change="event => (radioValue = event.target.value)" -->
			A형
		</label>
		<label>
			<input type="radio" name="type" value="B" v-model="radioValue" />
			<!-- :checked="radioValue === 'B'"
				@change="event => (radioValue = event.target.value)" -->
			B형
		</label>
		<label>
			<input type="radio" name="type" value="AB" v-model="radioValue" />
			<!-- :checked="radioValue === 'AB'"
				@change="event => (radioValue = event.target.value)" -->
			AB형
		</label>
		<label>
			<input type="radio" name="type" value="O" v-model="radioValue" />
			<!-- :checked="radioValue === 'O'"
				@change="event => (radioValue = event.target.value)" -->
			O형
		</label>
		<div>{{ radioValue }}</div>
		<hr />
		<h2>select value</h2>
		<select v-model="selectValue">
			<option value="html">HTML 수업</option>
			<option value="css">CSS 수업</option>
			<option value="javascript">JavaScript 수업</option>
		</select>
		{{ selectValue }}
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const inputValue = ref(null);
		const textareaValue = ref(null);
		const checkboxValue = ref(true);
		const checkboxValues = ref([]);
		const radioValue = ref('A');
		const selectValue = ref('html');
		return {
			inputValue,
			textareaValue,
			checkboxValue,
			checkboxValues,
			radioValue,
			selectValue,
		};
	},
};
</script>

<style lang="scss" scoped></style>
