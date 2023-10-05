<template>
	<div>
		<p>{{ message }}</p>
		<button @click="addMessage">add Click</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		let message = ref('Hello Vue3!');
		const addMessage = () => {
			message.value = message.value + '!';
		};

		console.log(message);
		console.log('message: ', message.value);
		console.log('message typeof: ', typeof message.value);

		return {
			message,
			addMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
