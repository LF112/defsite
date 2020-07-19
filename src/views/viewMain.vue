<template>
	<main>
		<div>
			<div class="mainWrapper">
				<this404 />
			</div>
		</div>
	</main>
</template>

<script>
import this404 from './this/404.vue'
export default {
	components: {
		this404
	}
}
</script>

<style lang="less" scoped>
@isHeight: calc(100vh - 40px);
main {
	position: relative;
	min-height: @isHeight;
	background-size: cover;
	background-position: 50%;
	overflow: initial;
	> div {
		width: 100%;
		padding: 0 25px;
		.mainWrapper {
			margin: 0 auto;
			position: relative;
			display: flex;
			justify-content: center;
			align-items: center;
			min-height: @isHeight;

			.fade-enter-active,
			.fade-leave-active {
				opacity: 1;
				transition: opacity 0.3s;
			}
			.fade-enter,
			.fade-leave-active {
				opacity: 0;
			}
		}
	}
}
@media screen and (max-width: 780px) {
	main {
		min-height: calc(100vh - 48px);
		> div {
			height: 100%;
			padding: 10px 10px;
		}
	}
}
</style>
