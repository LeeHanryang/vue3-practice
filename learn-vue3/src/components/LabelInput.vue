<template>
	<div>
		<label>
			<!-- v-model="username" -->
			<!-- <input
				:value="modelValue"
				@input="event => $emit('update:modelValue', event.target.value)"
				type="text"
			/> -->
			{{ label }}
			<input v-model="value" type="text" />
		</label>
	</div>
</template>

<script>
import { computed } from 'vue';

export default {
	// props: ['modelValue', 'label'],
	props: ['title', 'label'],
	// emits: ['update:modelValue'],
	emits: ['update:title'],
	setup(props, { emit }) {
		const value = computed({
			get() {
				// return props.modelValue;
				return props.title;
			},
			set(value) {
				// emit('update:modelValue', value);
				emit('update:title', value);
			},
		});
		return {
			value,
		};
	},
};
</script>

<style lang="scss" scoped></style>
