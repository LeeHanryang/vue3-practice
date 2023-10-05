<template>
	<div>
		<div
			class="text"
			:class="[isActive ? 'active-class' : 'class', errorClass, classObject]"
		>
			텍스트 입니다.
		</div>
		<button @click="toggle">toggle</button>
		<button @click="hasError = !hasError">toggleError</button>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const isActive = ref(true);
		const hasError = ref(false);

		// const classObject = reactive({
		// 	active: true,
		// 	error: false,
		// });

		const classObject = computed(() => {
			return {
				active: true,
				error: true,
				blue: true,
			};
		});

		const activeClass = ref('active');
		const errorClass = ref('error');

		const toggle = () => {
			isActive.value = !isActive.value;
		};

		return {
			classObject,
			isActive,
			hasError,
			toggle,
			activeClass,
			errorClass,
		};
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}
.error {
	color: orange;
}
</style>
