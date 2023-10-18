<template>
	<div>
		<main>
			<div class="container py-4">
				<!-- @click="sayHello" -->
				<MyButton class="my-button" id="my-button" @click="sayHello" />
				<LabelInput label="이름" data-id="id입니다." />
				<hr />
				<div>
					<FancyButton>Click!!<span style="color: red">@@@</span></FancyButton>
					<FancyButton #="{ fancyMessage }">{{ fancyMessage }}</FancyButton>
					<hr />
					<AppCard>
						<template #[slotArgs]="{ headerMessage }">{{
							headerMessage
						}}</template>
						<!-- <template #header>제목입니다.</template> -->
						<!-- <template #default>내용입니다.</template> -->
						<!-- 암시적으로 Default 슬롯 사용하기 -->
						<!-- <template #footer>밑글입니다.</template> -->
						<template #default="{ childMessage, helloMessage }">
							디폴트입니다. {{ message }}
							<br />
							{{ childMessage }}
							<br />
							{{ helloMessage }}
						</template>
						<template #footer="{ footerMessage }">
							{{ footerMessage }}</template
						>
					</AppCard>
					<AppCard> 게시글 입니다. </AppCard>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
import MyButton from '@/components/MyButton.vue';
import LabelInput from '@/components/LabelInput.vue';
import FancyButton from './FancyButton.vue';
import AppCard from './AppCard.vue';
import { ref } from 'vue';
export default {
	components: {
		MyButton,
		LabelInput,
		FancyButton,
		AppCard,
	},
	setup() {
		const sayHello = () => {
			alert('안녕하세요!');
		};

		const slotArgs = ref('header');
		const message = ref('안녕하세요.');
		return {
			sayHello,
			slotArgs,
			message,
		};
	},
};
</script>

<style lang="scss" scoped></style>
