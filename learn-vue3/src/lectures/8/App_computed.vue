<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p> -->
		<p>{{ hasLectuer }}</p>
		<p>{{ hasLectuer }}</p>
		<p>{{ hasLectuer }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<p>{{ existLecture() }}</p>
		<hr />
		<button @click="counter++">Counter : {{ counter }}</button>
		<hr />
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '이준혁',
			lectures: ['HTML/CSS', 'JavaScript', 'Vue3'],
		});

		const hasLectuer = computed(() => {
			console.log('computed');
			return teacher.lectures.length > 0 ? '있음' : '없음';
		});

		const existLecture = () => {
			console.log('method');
			return teacher.lectures.length > 0 ? '있음' : '없음';
		};

		const counter = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');

		// const fullName = computed(() => `${firstName.value} ${lastName.value}`);
		const fullName = computed({
			get() {
				return `${firstName.value} ${lastName.value}`;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});
		console.log('Console 출력 :', fullName.value);
		fullName.value = '이 준혁';

		return {
			teacher,
			hasLectuer,
			existLecture,
			counter,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
