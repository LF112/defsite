<template>
	<div class="statusCode">
		<div>
			<h2>{{ !isJson.code ? 404 : isJson.code }}</h2>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		isJson: Object
	}
}
</script>

<style lang="less" scoped>
.statusCode {
	position: relative;
	width: 100%;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
	> div {
		display: inline-flex;
		> h2 {
			color: #00bcd4;
			font-size: 65px;
			font-family: fontOne;
		}
	}
}
</style>
