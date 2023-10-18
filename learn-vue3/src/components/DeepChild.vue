<template>
	<div class="card">
		<div class="card-header">Deep Child Component</div>
		<div class="card-body">
			staticMessage: {{ staticMessage }}
			<br />
			message: {{ message }}
			<br />
			count: {{ count }}
			<br />
			app-message: {{ appMessage }}
		</div>
	</div>
</template>

<script>
import { inject } from 'vue';

export default {
	setup() {
		const staticMessage = inject('static-message', 'default message');
		const { message, updateMessage } = inject('message');
		const count = inject('count');
		message.value = message.value + '!';
		updateMessage('!!!');
		const appMessage = inject('app-message');

		return {
			staticMessage,
			message,
			count,
			appMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
