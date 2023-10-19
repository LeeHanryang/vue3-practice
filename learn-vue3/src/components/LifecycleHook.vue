<template>
	<div class="container py-4">
		<input ref="inputRef" type="text" />
		<button @click="visible = !visible">Toggle Child</button>
		<LifecycleChild v-if="visible"></LifecycleChild>
		<p id="message">{{ message }}</p>
	</div>
</template>

<script>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
import LifecycleChild from './LifecycleChild.vue';

export default {
	components: {
		LifecycleChild,
	},
	setup() {
		// console.log('setup');
		const inputRef = ref(null);
		const message = ref('');
		const visible = ref(false);

		// onBeforeMount(() => {
		// 	console.log('onBeforMount', inputRef.value);
		// });

		// onMounted(() => {
		// 	console.log('onMounted', inputRef.value.value);
		// });
		// onBeforeUpdate(() => {
		// 	console.log('onBeforeUpdate', message.value);
		// 	console.log(
		// 		'DOM Content',
		// 		document.querySelector('#message').textContent,
		// 	);
		// });

		// onUpdated(() => {
		// 	console.log('onUpdated');
		// 	console.log(
		// 		'DOM Content',
		// 		document.querySelector('#message').textContent,
		// 	);
		// });

		return {
			inputRef,
			message,
			visible,
		};
	},
	// data: () => ({
	// 	dataMessage: 'data Message',
	// }),
	// beforeCreate() {
	// 	console.log('beforCreate', this.dataMessage);
	// },
	// created() {
	// 	console.log('create', this.dataMessage);
	// },
};
</script>

<style lang="scss" scoped></style>
