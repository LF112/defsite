<template>
	<div id="FUTIWOLF">
		<viewMain />
	</div>
</template>

<script>
import viewMain from '@/views/viewMain'

export default {
	components: {
		viewMain
	}
}
</script>

<style lang="less">
*,
body,
html {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
	border: 0;
	background: 0 0;
	word-wrap: break-word;
	text-decoration: none;
	-webkit-tap-highlight-color: transparent;
	font-family: Titillium Web, -apple-system, system-ui, BlinkMacSystemFont,
		Segoe UI, Roboto, PingFang SC, Hiragino Sans GB, Microsoft YaHei,
		Helvetica Neue, sans-serif;
}

body {
	position: relative;
	background: hsl(207, 22%, 90%);
}

a,
span {
	color: hsla(0, 0%, 100%, 0.19);
	text-decoration: none;
	font-weight: lighter;
	font-size: 12px;
	cursor: pointer;
}

:not(body, .statusCode) {
	transition: all 0.5s cubic-bezier(0.22, 0.58, 0.12, 0.98);
}

@font-face {
	font-family: 'fontOne';
	font-display: swap;
	src: url('https://cdn.lfio.net/site/static/404/this.ttf') format('truetype');
}

#__SVG_SPRITE_NODE__ {
	display: none;
}

/* ---- */
.TIP::after {
	position: absolute;
	bottom: 100%;
	left: 50%;
	z-index: 300;
	display: block;
	overflow: hidden;
	padding: 2px 5px;
	max-width: 320px;
	border-radius: 2px;
	background: rgba(79, 89, 95, 0.4);
	color: #fff;
	content: attr(data-tooltip);
	text-overflow: ellipsis;
	white-space: pre;
	font-weight: lighter;
	font-size: 0.7rem;
	line-height: 20px;
	opacity: 0;
	transition: opacity 0.2s, transform 0.2s;
	transform: translate(-50%, 0.4rem);
	pointer-events: none;
}

.TIP:focus::after,
.TIP:hover::after {
	opacity: 1;
	transform: translate(-50%, -0.2rem);
}

::-webkit-scrollbar {
	width: 6px;
	height: 6px;
	border-radius: 6px;
	background: rgba(0, 0, 0, 0.05);
	-webkit-appearance: none;
}

::-webkit-scrollbar-button,
::-webkit-scrollbar-corner,
::-webkit-scrollbar-track,
::-webkit-scrollbar-track-piece {
	display: none;
	background: 0 0;
}

::-webkit-scrollbar-button,
::-webkit-scrollbar-corner,
::-webkit-scrollbar-track,
::-webkit-scrollbar-track-piece {
	display: none;
	background: 0 0;
}

::-webkit-scrollbar-thumb {
	width: 4px;
	height: 4px;
	border-radius: 6px;
	background-color: rgba(0, 0, 0, 0.2);
}

::-webkit-scrollbar-button,
::-webkit-scrollbar-corner,
::-webkit-scrollbar-track,
::-webkit-scrollbar-track-piece {
	display: none;
	background: 0 0;
}

::-webkit-scrollbar-button,
::-webkit-scrollbar-corner,
::-webkit-scrollbar-track,
::-webkit-scrollbar-track-piece {
	display: none;
	background: 0 0;
}

::selection {
	background: #b2b8c1;
	color: #0bf;
}
</style>
