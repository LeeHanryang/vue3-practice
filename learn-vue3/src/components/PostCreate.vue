<template>
	<div class="row g-3">
		<!-- @click="$emit('createPost', 1, 2, 3, '김길동')" -->
		<div class="col col-2">
			<select
				v-model="type"
				class="form-select"
				aria-label="Default select example"
			>
				<option value="news">뉴스</option>
				<option value="notice">공지사항</option>
			</select>
		</div>
		<div class="col col-3">
			<input v-model="title" type="text" class="form-control" />
		</div>
		<div class="col col-5">
			<input v-model="contents" type="text" class="form-control" />
		</div>
		<div class="col col-2 d-grid">
			<button class="btn btn-primary" @click="createPost">추가</button>
		</div>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	// emits: ['createPost'],
	emits: {
		createPost: ({ type, title, contents }) => {
			if (!type || !title || !contents) false;
			return true;
		},
	},
	setup(props, { emit }) {
		const type = ref('news');
		const title = ref('');
		const contents = ref('');

		const createPost = () => {
			const newPost = {
				type: type.value,
				title: title.value,
				contents: contents.value,
			};
			emit('createPost', newPost);
			type.value = 'news';
			title.value = '';
			contents.value = '';
		};
		return {
			createPost,
			type,
			title,
			contents,
		};
	},
};
</script>

<style lang="scss" scoped></style>
