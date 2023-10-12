<template>
	<div>
		<p>{{ message }}</p>
		<p>{{ reverseMessage }}</p>
	</div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const message = ref('Hello Vue3');
		const reverseMessage = ref('');

		const reverseFunction = newValue => {
			console.log('즉시 실행함.');
			reverseMessage.value = newValue.split('').reverse().join('');
		};
		watch(message, reverseFunction, {
			immediate: true,
		});

		return {
			message,
			reverseMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
