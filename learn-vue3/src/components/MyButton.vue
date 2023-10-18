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
	// inheritAttrs: false,
	emits: ['click'],
	setup(props, { emit }) {
		// console.log(attrs);
		// console.log(attrs.class);
		// console.log(attrs.id);
		// console.log(attrs.onClick);
		// attrs.onClick();

		const sayHello = () => {
			emit('click');
		};
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
