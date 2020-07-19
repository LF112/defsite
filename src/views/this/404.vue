<template>
	<div class="this404">
		<div class="top">
			<div>
				<div class="siteUrl">
					<i class="el-icon-link"></i>
					<p>{{ HOST }}</p>
				</div>
				<statusCode :isJson="isJson" />
				<isCircle />
			</div>
		</div>
		<menuMain :isJson="isJson" />
		<div class="bottom">
			<div class="content">
				<p>{{ !isJson.Info ? '页面不存在' : isJson.Info }}</p>
			</div>
			<div class="futi">
				<isIcon i="futi"></isIcon>
				<p>
					Copyright &copy; 2017 - {{ new Date().getFullYear() }}
					<a href="https://www.lf112.net" class="LF">LF112</a>
					All Rights Reserved.
				</p>
			</div>
		</div>
	</div>
</template>

<script>
import statusCode from '@/components/this/statusCode'
import menuMain from '@/components/this/menuMain'
import isCircle from '@/components/this/circle'
export default {
	mounted() {
		const isDoc = document.getElementById('LF112'),
			errorJson = { code: 500, Info: '该页面异常' }
		if (isDoc == null) this.isJson = errorJson
		else if (
			isDoc.getAttribute('futi-json') == null ||
			isDoc.getAttribute('futi-json') == ''
		)
			this.isJson = errorJson
		else
			try {
				this.isJson = JSON.parse(
					document.getElementById('LF112').getAttribute('futi-json')
				)
			} catch (e) {
				this.isJson = errorJson
			}
		if (this.isJson.siteName)
			document.title =
				this.isJson.code +
				' - ' +
				this.isJson.Info +
				' | ' +
				this.isJson.siteName
		else document.title = this.isJson.code + ' - ' + this.isJson.Info
	},
	data() {
		return {
			HOST: location.host,
			isJson: {}
		}
	},
	components: {
		statusCode,
		menuMain,
		isCircle
	}
}
</script>

<style lang="less" scoped>
@radiusFrame: 5px;

.this404 {
	position: relative;
	width: 875px;
	height: auto;
	box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3);
	border-radius: @radiusFrame;
	> div {
		width: 100%;
		height: 256px;
		position: relative;
	}
	.top {
		background-color: #f7fbff;
		border-radius: @radiusFrame @radiusFrame 0 0;
		> div {
			position: relative;
			padding: 4px;
			height: 100%;
			.siteUrl {
				position: absolute;
				display: flex;
				align-items: center;
				padding-top: 10px;
				padding-left: 14px;
				user-select: none;
				> i {
					font-size: 14px;
					font-weight: 600;
					color: hsla(199, 11%, 57%, 0.52);
					margin-right: 5px;
					line-height: 1;
				}
				> p {
					font-size: 14px;
					font-weight: 600;
					text-transform: uppercase;
					color: hsla(199, 11%, 57%, 0.52);
				}
			}
		}
	}
	.bottom {
		background: linear-gradient(162deg, #37eff9, #64c6f4, #64c0ec);
		border-radius: 0 0 @radiusFrame @radiusFrame;
		.content {
			position: relative;
			height: calc(100% - 32px);
			width: 100%;
			display: flex;
			align-items: center;
			justify-content: center;
			> p {
				text-align: center;
				color: #fff;
				font-size: 30px;
				font-weight: lighter;
				letter-spacing: 2px;
				margin-bottom: -32px;
			}
		}
		.futi {
			position: absolute;
			width: 100%;
			height: 32px;
			padding: 0 15px;
			z-index: 10;
			display: flex;
			align-items: center;
			> svg {
				width: 52px;
				height: 18px;
				padding-right: 15px;
				border-right: 1px solid hsla(0, 0%, 100%, 0.72);
			}
			> p {
				line-height: 32px;
				font-size: 12px;
				color: hsla(0, 0%, 100%, 0.69);
				font-weight: lighter;
				margin-left: 15px;
				.LF {
					font-family: fontOne;
					color: hsla(0, 0%, 100%, 0.96);
					font-weight: 700;
				}
			}
		}
	}
}
@mobile_bottom: 50px;
@media screen and (max-width: 780px) {
	.this404 {
		.bottom {
			.content {
				height: calc(100% - @mobile_bottom);
				> p {
					margin-bottom: -@mobile_bottom;
				}
			}
			.futi {
				height: @mobile_bottom;
				display: block;
				text-align: center;
				> svg {
					border-right: unset;
					padding-right: unset;
				}
				> p {
					line-height: unset;
					margin-left: unset;
				}
			}
		}
	}
}
</style>
