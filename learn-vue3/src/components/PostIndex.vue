<template>
	<div>
		<main>
			<div class="container py-4">
				<PostCreate @create-post="createPost" />
				<hr class="my-4" />
				<div class="row g-3">
					<div v-for="post in posts" :key="post.id" class="col col-4">
						<PostItem
							:title="post.title"
							:contents="post.contents"
							:type="post.type"
							:is-like="post.isLike"
							@toggle-like="post.isLike = !post.isLike"
						/>
					</div>
				</div>

				<hr class="my-4" />
				<LabelInput
					v-model:title="username"
					label="이름"
					class="parent-class"
					style="color: red"
					id="parent-id"
				/>
			</div>
		</main>
	</div>
</template>

<script>
import PostItem from '@/components/PostItem.vue';
import PostCreate from '@/components/PostCreate.vue';
import LabelInput from '@/components/LabelInput.vue';
import { reactive, ref } from 'vue';

export default {
	components: {
		PostItem,
		PostCreate,
		LabelInput,
	},
	setup() {
		const posts = reactive([
			{
				id: '1',
				title: '제목1',
				contents: '내용1',
				isLike: false,
				type: 'news',
			},
			{
				id: '2',
				title: '제목2',
				contents: '내용2',
				isLike: true,
				type: 'news',
			},
			{
				id: '3',
				title: '제목3',
				contents: '내용3',
				isLike: true,
				type: 'news',
			},
			{
				id: '4',
				title: '제목4',
				contents: '내용4',
				isLike: true,
				type: 'news',
			},
			{
				id: '5',
				title: '제목5',
				contents: '내용5',
				isLike: false,
				type: 'notice',
			},
			{
				id: '6',
				title: '제목6',
				contents: '내용6',
				isLike: false,
				type: 'notice',
			},
		]);
		const createPost = newPosts => {
			console.log('createPost', newPosts);
			posts.push(newPosts);
		};
		const username = ref('');
		return {
			posts,
			createPost,
			username,
		};
	},
};
</script>

<style lang="scss" scoped></style>
