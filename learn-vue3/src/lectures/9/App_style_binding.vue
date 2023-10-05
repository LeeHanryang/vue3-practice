<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur, non
			nemo nobis praesentium cupiditate illum quisquam ut impedit exercitationem
			laboriosam a sequi. Facilis voluptatum sint et dolore impedit cumque
			quaerat!
		</div>
		<button @click="fontSize++">+</button>
		<button @click="fontSize--">-</button>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		// const styleObjct = reactive({
		// 	color: 'red',
		// 	fontSize: '13px',
		// });
		const fontSize = ref(13);
		const styleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontSize.value + 'px',
			};
		});
		return {
			styleObject,
			fontSize,
		};
	},
};
</script>

<style lang="scss" scoped></style>
