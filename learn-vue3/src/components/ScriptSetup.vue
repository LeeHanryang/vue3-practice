<template>
	<div class="container py-4">
		{{ msg }}
		<br />
		{{ message }}
		<input v-model="message" type="text" />
		<button @click="sayHello">button</button>
		<PostItem type="news" title="제목" contents="내용" :is-like="true" />
		<PostItem type="news" title="제목" contents="내용" :is-like="true" />
		<PostItem type="news" title="제목" contents="내용" :is-like="true" />
		<PostItem type="news" title="제목" contents="내용" :is-like="true" />
		<hr />
		<TemplateRefChildVue ref="child"></TemplateRefChildVue>
		<template v-if="child">{{ child.message }}</template>
		<hr />
		<MyButtonVue class="parent-class"></MyButtonVue>
	</div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';
import PostItem from '@/components/setup/PostItem.vue';
import TemplateRefChildVue from './setup/TemplateRefChild.vue';
import MyButtonVue from './setup/MyButton.vue';

const msg = 'Hello World!';
const message = ref('');
const sayHello = () => {
	alert('Hello World!!!');
};

const child = ref(null);

defineExpose({
	msg,
	message,
	sayHello,
});

const response = await axios(
	'https://dummy.restapiexample.com/api/v1/employees',
).then(response => console.log('response:', response));

// async function callApi(params) {
// 	await axios('https://dummy.restapiexample.com/api/v1/employees').then(
// 		response => console.log('response:', response),
// 	);
// }
// callApi();
</script>

<style lang="scss" scoped></style>
