<template>
	<label class="form-label" id="child-id">
		{{ label }}
	</label>
	<input v-model="value" v-bind="$attrs" type="text" class="form-control" />
</template>

<script>
import { computed } from 'vue';

export default {
	props: ['title', 'label'],
	emits: ['update:title'],
	setup(props, { emit }) {
		const value = computed({
			get() {
				return props.title;
			},
			set(value) {
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
