<template>
	<div>
		<main>
			<div class="container py-4">
				<!-- @click="sayHello" -->
				<MyButton class="my-button" id="my-button" @click="sayHello" />
				<LabelInput label="이름" data-id="이름입니다." />
			</div>
		</main>
	</div>
</template>

<script>
import MyButton from '@/components/MyButton.vue';
import LabelInput from '@/components/LabelInput.vue';

export default {
	components: {
		MyButton,
		LabelInput,
	},
	setup() {
		const sayHello = () => {
			alert('안녕하세요!');
		};
		return {
			sayHello,
		};
	},
};
</script>

<style lang="scss" scoped></style>
