<template>
	<div class="menuMain">
		<div>
			<div
				:data-tooltip="isHTTPS ? '页面受到 HTTPS 保护' : '页面不安全'"
				class="TIP"
			>
				<i
					:class="isHTTPS ? 'el-icon-lock' : 'el-icon-unlock'"
					:style="
						isHTTPS ? 'color: rgb(26, 228, 69)' : 'color: hsl(4, 90%, 58%)'
					"
				></i>
			</div>
			<div class="isPath">
				<p>{{ isPATH }}</p>
			</div>
			<a :href="isJson.url ? isJson.url : 'https://www.lf112.net'">
				<div data-tooltip="主站" class="TIP">
					<i class="el-icon-right" style="color: #00e8ff;"></i>
				</div>
			</a>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		isJson: Object
	},
	data() {
		return {
			isHTTPS: 'https:' == document.location.protocol ? true : false,
			isPATH: location.pathname
		}
	}
}
</script>

<style lang="less" scoped>
.menuMain {
	top: 0;
	height: 100% !important;
	position: absolute !important;
	display: flex;
	align-items: center;
	justify-content: center;
	z-index: 1;
	> div {
		display: flex;
		align-items: center;
		.TIP {
			cursor: pointer;
		}
		.isPath {
			width: 350px;
			padding: 0 10px;
			> p {
				color: hsla(33, 100%, 51%, 0.92);
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
			}
		}
		div {
			position: relative;
			width: 45px;
			height: 45px;
			margin: 0 10px;
			background: #f9fdff;
			border-radius: 5px;
			box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3);
			display: flex;
			align-items: center;
			justify-content: center;
			user-select: none;
			> i {
				color: #333;
				font-size: 22px;
				font-weight: bolder;
			}
		}
	}
}
@media screen and (max-width: 780px) {
	.menuMain {
		> div {
			div {
				height: 35px;
				width: 35px;
				margin: 0 5px;
				> i {
					font-size: 12px;
				}
			}
			.isPath {
				width: 185px !important;
			}
		}
	}
}
</style>
