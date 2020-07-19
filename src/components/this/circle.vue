<template>
	<div class="Circle">
		<div>
			<svg viewBox="0 0 100 100">
				<defs>
					<filter id="shadow">
						<feDropShadow
							dx="0"
							dy="0"
							stdDeviation="1.5"
							flood-color="hsla(199, 85%, 67%, 0.45)"
						/>
					</filter>
				</defs>
				<circle
					id="spinner"
					style="fill:transparent;stroke:hsla(199, 85%, 67%, 0.45);stroke-width: 7px;stroke-linecap: round;filter:url(#shadow);"
					cx="50"
					cy="50"
					r="45"
				/>
			</svg>
		</div>
	</div>
</template>

<style lang="less" scoped>
.Circle {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: flex-end;
	overflow: hidden;

	> div {
		width: 250px;
		height: 250px;
		margin-bottom: -180px;
		margin-right: -50px;

		@keyframes animation {
			0% {
				stroke-dasharray: 1 98;
				stroke-dashoffset: -105;
			}
			50% {
				stroke-dasharray: 80 10;
				stroke-dashoffset: -160;
			}
			100% {
				stroke-dasharray: 1 98;
				stroke-dashoffset: -300;
			}
		}

		#spinner {
			transform-origin: center;
			animation-name: animation;
			animation-duration: 1.2s;
			animation-timing-function: cubic-bezier;
			animation-iteration-count: infinite;
		}
	}
}
@media screen and (max-width: 780px) {
	.Circle {
		> div {
			width: 150px;
			height: 150px;
		}
	}
}
</style>
