<template>
	<div class="pbs-c-hovered-show" ref="wheelCenter">
		<svg
			class="pbs-c-wheel-left-arc"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 500 500"
		>
			<path
				d="M500,0C223.86,0,0,223.86,0,500V0H500Z"
				fill="transparent"
			/>
		</svg>

		<svg
			class="pbs-c-wheel-right-arc"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 500 500"
		>
			<path
				d="M0,0C276.14,0,500,223.86,500,500V0H0Z"
				fill="transparent"
			/>
		</svg>

		<p
			v-if="hoveredShow"
			:style="{
				fontSize: `${showFontSize}px`,
			}"
		>
			{{ hoveredShow.title }}
		</p>
	</div>
</template>

<script>
export default {
	name: 'WheelCenter',
	data() {
		return {
			wheelCenterWidth: null,
		};
	},
	props: {
		focusedShow: {
			type: Object,
		},
		hoveredShow: {
			type: Object,
		},
	},
	mounted() {
		const data = this;

		data.wheelCenterWidth = this.$refs.wheelCenter.offsetWidth;

		window.addEventListener('resize', () => {
			data.wheelCenterWidth = this.$refs.wheelCenter.offsetWidth;
		});
	},
	computed: {
		showFontSize() {
			return this.wheelCenterWidth / 10;
		},
	},
};
</script>

<style lang="scss" scoped>
.pbs-c-hovered-show {
	height: 50%;
	left: 50%;
	overflow: hidden;
	position: absolute;
	top: 50%;
	transform: translate(-50%, -50%);
	width: 50%;
}

svg {
	height: auto;
	width: 50%;
}

.pbs-c-wheel-left-arc {
	float: left;
	shape-outside: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 500 500' %3E%3Cpath d='M500,0C223.86,0,0,223.86,0,500V0H500Z' /%3E%3C/svg%3E");
}

.pbs-c-wheel-right-arc {
	float: right;
	shape-outside: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 500 500' %3E%3Cpath d='M0,0C276.14,0,500,223.86,500,500V0H0Z' /%3E%3C/svg%3E");
}

p {
	color: var(--pbs-orange-400);
	display: block;
	hyphens: auto;
	line-height: 1.25;
	margin: 0;
	position: relative;
	text-align: center;
	top: 26.5%;
	transform: translate(0, -50%);
}
</style>
