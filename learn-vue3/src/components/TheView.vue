<template>
	<div>
		<main>
			<div class="container py-4">
				<div class="row g-3">
					<div class="col col-4">
						<!-- <AppCard /> -->
						<app-card />
					</div>
					<div class="col col-4">
						<AppCard />
					</div>
					<div class="col col-4">
						<AppCard />
					</div>
					<div class="col col-4">
						<AppCard />
					</div>
					<div class="col col-4">
						<AppCard />
					</div>
					<div class="col col-4">
						<AppCard />
					</div>
				</div>
			</div>
		</main>
	</div>
</template>

<script>
console.log('App Card Module()');
import AppCard from '@/components/AppCard.vue';

export default {
	components: {
		AppCard,
	},
	setup() {
		console.log('App Card Setup()');
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
