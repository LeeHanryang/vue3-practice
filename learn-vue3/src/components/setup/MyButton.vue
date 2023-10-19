<template>
	<div class="p-3 bg-danger">
		<!-- v-bind="$attrs" -->
		<button class="btn btn-primary" type="button" @click="sayHello">
			My Button
		</button>
		<!-- {{ $attrs }} -->
	</div>
</template>

<script>
export default {
	inheritAttrs: false,
};
</script>

<script setup>
const emit = defineEmits(['click']);

const sayHello = () => {
	emit('click');
};
</script>

<style lang="scss" scoped></style>
