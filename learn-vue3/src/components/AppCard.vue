<template>
	<div>
		<div class="card">
			<div class="card-body">
				<!-- {{ classes }} -->
				<h5 class="card-title color">Card title</h5>
				<!-- <p class="card-text" :class="$style.red"> -->
				<!-- <p class="card-text" :class="classes.red"> -->
				<p class="card-text">
					Some quick example text to build on the card title and make up the
					bulk of the card's content.
				</p>
				<a href="#" class="btn btn-primary">Go somewhere</a>
			</div>
		</div>
	</div>
</template>

<script>
import { ref, useCssModule } from 'vue';

console.log('App Card Module()');
export default {
	setup() {
		// const style = useCssModule();
		// console.log('style:', style);
		console.log('App Card Setup()');

		const color = ref('red');
		color.value = 'yellow';
		return { color };
	},
};
</script>

<style scoped>
.color {
	color: v-bind(color) !important;
}
</style>

<!-- <style module="classes">
.red {
	color: red !important;
}
</style> -->

<!-- <style module>
.red {
	color: red !important;
}
</style> -->

<!-- <style scoped>
.red {
	color: red;
}
</style> -->
