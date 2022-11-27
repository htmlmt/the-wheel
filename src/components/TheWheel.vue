<template>
	<div
		:class="wheelStateClass"
		:style="{
			marginBottom: wheelMarginBottom + 'px',
		}"
		class="pbs-c-wheel"
		v-if="shuffledShows"
	>
		<h2 class="pbs-u-sr-only">Shows</h2>

		<button
			aria-hidden="true"
			class="pbs-c-rotate-wheel pbs-v-rotate-wheel-left"
			type="button"
			@click="shiftShowsClockwise"
			@mouseenter="enterLeftRotate"
			@mouseleave="leaveLeftRotate"
		>
			<span class="pbs-u-sr-only">Rotate wheel clockwise</span>

			<svg class="pbs-c-rotate-arrow pbs-v-rotate-arrow-left">
				<use xlink:href="#wheel-menu-arrow"></use>
			</svg>
		</button>

		<div class="pbs-c-wheel-container">
			<div
				class="pbs-c-wheel-shows"
				:style="{
					rotate: `${wheelRotation}deg`,
				}"
			>
				<WheelShows
					@focus-or-hover-show="focusOrHoverShow"
					:shuffledShows="shuffledShows"
					:totalWedges="totalWedges"
					:visibleShows="visibleShows"
				/>

				<WheelWedges :totalWedges="totalWedges" />
			</div>

			<WheelCenter :hoveredShow="hoveredShow" />
		</div>

		<button
			aria-hidden="true"
			class="pbs-c-rotate-wheel pbs-v-rotate-wheel-right"
			type="button"
			@click="shiftShowsCounterClockwise"
			@mouseenter="enterRightRotate"
			@mouseleave="leaveRightRotate"
		>
			<span class="pbs-u-sr-only">Rotate wheel counter-clockwise</span>
			<svg class="pbs-c-rotate-arrow pbs-v-rotate-arrow-right">
				<use xlink:href="#wheel-menu-arrow"></use>
			</svg>
		</button>

		<div class="pbs-c-wheel-all-shows">
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 372.12 98.24">
				<a xlink:href="https://pbskids.org/everything">
					<g>
						<path
							class="pbs-c-wheel-all-shows-background"
							d="M0,32.08,22.86,98.24a503,503,0,0,1,326.41-2l22.85-66.15A572.79,572.79,0,0,0,0,32.08Z"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M110.75,44.29l2.09-11.72,4.41,10.8ZM102.6,55.55l7,.51c0-.24.06-.68.12-1.33s.14-1.3.23-2,.22-1.61.33-2.55l8.61-1.14c.38,1,.7,1.81,1,2.57a19.35,19.35,0,0,1,.76,2.65q1.81-.6,3.63-1c1.21-.3,2.42-.64,3.63-1l-1.91-4-2.16-4.52c-.75-1.55-1.51-3.12-2.28-4.69s-1.53-3.11-2.24-4.6-1.41-2.9-2.07-4.23-1.25-2.52-1.75-3.55c-.48,0-1.06.1-1.73.18l-2,.27-1.94.27-1.49.22c-.09.39-.2.94-.34,1.64s-.3,1.49-.49,2.37-.38,1.81-.58,2.81-.39,2-.58,3-.39,1.9-.57,2.8-.35,1.7-.49,2.39Z"
						/>
						<polygon
							class="pbs-c-wheel-all-shows-text"
							points="130.32 52.54 136.88 51.76 133.28 22.47 127.27 22.85 130.32 52.54"
						/>
						<polygon
							class="pbs-c-wheel-all-shows-text"
							points="140.32 51.51 146.89 50.85 143.84 21.5 137.83 21.77 140.32 51.51"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M160.05,48.7a25.2,25.2,0,0,0,5.29,1,45.33,45.33,0,0,0,5.41.13,12.81,12.81,0,0,0,3.42-.6,9.94,9.94,0,0,0,3-1.56,8,8,0,0,0,2.15-2.52,6.6,6.6,0,0,0,.73-3.45,6.25,6.25,0,0,0-1-3.36,10.16,10.16,0,0,0-2.35-2.46,17.76,17.76,0,0,0-3-1.81l-3-1.44a14.08,14.08,0,0,1-2.31-1.38,2.11,2.11,0,0,1-1-1.59,1.39,1.39,0,0,1,.33-1,2.43,2.43,0,0,1,.94-.61,5.33,5.33,0,0,1,1.21-.28c.42,0,.79-.06,1.12-.08.71,0,1.38,0,2,0a13,13,0,0,1,1.8.24,14.18,14.18,0,0,1,1.75.47l1.88.64,1-6.15a19,19,0,0,0-4.48-1.24,24.16,24.16,0,0,0-4.67-.29,16.19,16.19,0,0,0-4,.62A10.72,10.72,0,0,0,163,23.59a7.55,7.55,0,0,0-2.36,2.77,8,8,0,0,0-.79,4,6.36,6.36,0,0,0,.94,3.25A10,10,0,0,0,162.89,36a15.29,15.29,0,0,0,2.74,1.77l2.71,1.38a15.18,15.18,0,0,1,2.09,1.24,1.82,1.82,0,0,1,.87,1.38,1,1,0,0,1-.41.93,3.52,3.52,0,0,1-1,.54,5.26,5.26,0,0,1-1.25.27c-.44,0-.81.07-1.1.08a10.29,10.29,0,0,1-3.36-.44c-1.1-.33-2.18-.68-3.27-1Z"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M183.5,19.45l-.15,29.61,6.33,0-.18-12.33a11.51,11.51,0,0,1,1.77-1.88,3.72,3.72,0,0,1,2.59-.88,1.2,1.2,0,0,1,1,.54,4.67,4.67,0,0,1,.66,1.38,10.73,10.73,0,0,1,.37,1.89c.07.69.11,1.38.12,2s0,1.27,0,1.82V43c0,1,0,2,0,3s-.05,2-.08,3.05l6.17.19c0-1.73-.05-3.45,0-5.17,0-.68,0-1.36,0-2V40.17c0-1.79,0-3.61,0-5.43a9.8,9.8,0,0,0-.48-2.86,8,8,0,0,0-1.28-2.45,6,6,0,0,0-4.91-2.37,5.82,5.82,0,0,0-3.21.87,13.26,13.26,0,0,0-2.61,2.16l0-10.47Z"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M211,37.86a9.49,9.49,0,0,1,.4-2.07,5.37,5.37,0,0,1,.83-1.62,3.47,3.47,0,0,1,1.23-1,3.32,3.32,0,0,1,1.71-.32,3.28,3.28,0,0,1,1.81.58,3.87,3.87,0,0,1,1.18,1.36,6.27,6.27,0,0,1,.62,1.83,9.36,9.36,0,0,1,.13,2,7,7,0,0,1-.45,2.22,5.5,5.5,0,0,1-1,1.66,4.09,4.09,0,0,1-1.35,1,3.36,3.36,0,0,1-1.55.31,2.9,2.9,0,0,1-1.54-.54,4,4,0,0,1-1.17-1.31,7.76,7.76,0,0,1-.73-1.86,6.56,6.56,0,0,1-.17-1.73C210.94,38.17,211,38,211,37.86Zm-6,.94a14.32,14.32,0,0,0,.34,3.75,10.32,10.32,0,0,0,1.55,3.61,9.16,9.16,0,0,0,3,2.82,10.23,10.23,0,0,0,4.78,1.28,8.49,8.49,0,0,0,7.78-3.58,10.48,10.48,0,0,0,1.65-3.61,18.78,18.78,0,0,0,.54-3.44l0-.31a16.08,16.08,0,0,0-.39-3.78,12.58,12.58,0,0,0-1.46-3.78,9.62,9.62,0,0,0-2.8-3,8.39,8.39,0,0,0-4.4-1.41h-.17a8.47,8.47,0,0,0-4.42.82,9.55,9.55,0,0,0-3.26,2.66,12.57,12.57,0,0,0-2,3.79A15.73,15.73,0,0,0,205,38.8Z"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M227.43,29.32a26.69,26.69,0,0,0,.27,3.25c.16,1.24.38,2.55.64,3.94s.54,2.78.85,4.22.63,2.8.94,4.09.62,2.46.92,3.51.53,1.88.74,2.49l6.29.59c.14-.31.37-.78.69-1.42s.66-1.37,1-2.22.8-1.77,1.25-2.79.89-2.06,1.33-3.14c.24,1,.5,2.07.75,3.07s.52,2,.78,2.86.49,1.72.72,2.46.42,1.37.57,1.87l6.31.67c.19-.38.47-1,.86-1.8s.83-1.77,1.31-2.84,1-2.23,1.53-3.47,1-2.45,1.56-3.66c.4-1,.78-2,1.14-2.91s.7-1.82,1-2.65l.8-2.2.56-1.56-6.38-.94L253.57,32l-.45,1.56c-.16.56-.33,1.12-.51,1.67s-.34,1-.46,1.47-.33,1-.63,1.87-.6,1.7-.9,2.59-.75,2.13-1.13,3.3c-.32-1.19-.61-2.3-.88-3.35-.23-.87-.46-1.76-.7-2.65s-.39-1.58-.48-2-.17-.91-.24-1.48-.14-1.14-.21-1.73-.13-1.14-.19-1.67-.12-1-.16-1.31l-1.13-.13-1.72-.21L242,29.61l-1.33-.2-1.77,5.9c-.12.41-.34,1-.65,1.87s-.62,1.68-.92,2.54-.79,2.08-1.21,3.22c-.2-1.08-.41-2.11-.61-3.07s-.31-1.66-.44-2.49-.22-1.45-.26-1.86l-.42-6.91-1.36.11-1.84.16c-.65.05-1.31.12-2,.2S227.94,29.24,227.43,29.32Z"
						/>
						<path
							class="pbs-c-wheel-all-shows-text"
							d="M260.33,52.51a20.33,20.33,0,0,0,4.41,2.15,28.76,28.76,0,0,0,4.79,1.14,6,6,0,0,0,2.52-.15,7.25,7.25,0,0,0,2.35-1.06,6.88,6.88,0,0,0,1.81-1.8,5.56,5.56,0,0,0,.94-2.34,6.2,6.2,0,0,0-.21-2.93,9,9,0,0,0-1.29-2.46,13.57,13.57,0,0,0-1.83-2c-.67-.6-1.3-1.15-1.89-1.63s-1.08-.92-1.47-1.29-.56-.68-.52-.93a1,1,0,0,1,.34-.66,1.43,1.43,0,0,1,.65-.29,3.48,3.48,0,0,1,.8-.05c.28,0,.52.05.73.08a8.1,8.1,0,0,1,2.47.78c.78.39,1.54.79,2.28,1.21l1.86-5.15a21.32,21.32,0,0,0-3.81-1.52,31.44,31.44,0,0,0-4-.88,9.13,9.13,0,0,0-2.81,0,7.94,7.94,0,0,0-2.63.89,6.81,6.81,0,0,0-2,1.73,5.24,5.24,0,0,0-1.07,2.54,4.6,4.6,0,0,0,.26,2.48,8.11,8.11,0,0,0,1.31,2.16,15,15,0,0,0,1.85,1.89L268,46a13.77,13.77,0,0,1,1.43,1.37,1.49,1.49,0,0,1,.46,1.19c-.08.52-.33.81-.76.87a4.6,4.6,0,0,1-1.23,0,7.85,7.85,0,0,1-1.46-.4,12.26,12.26,0,0,1-1.57-.73,13.52,13.52,0,0,1-1.47-.92q-.69-.48-1.23-.93Z"
						/>
						<polygon
							class="pbs-c-wheel-all-shows-text"
							points="297,40 295,58.24 314,52"
						></polygon>
					</g>
				</a>
			</svg>
		</div>

		<svg
			class="pbs-u-hidden"
			version="1.1"
			xmlns="http://www.w3.org/2000/svg"
			xmlns:xlink="http://www.w3.org/1999/xlink"
		>
			<symbol id="wheel-menu-arrow" viewBox="0 0 49.32 75.58">
				<g>
					<g>
						<path
							d="M33.06,45.09c.38-1.27,4.19-16,.41-26.92C29.5,6.72,18.28,0,18.28,0L1.76,10.4s8.87,5.5,12.72,15.36c2.8,7.19,2.78,13.05,2.45,15.3L0,36.83,14.53,75.58,49.32,49.16Z"
							fill="var(--pbs-orange-400)"
						></path>
					</g>
				</g>
			</symbol>
		</svg>
	</div>
</template>

<script>
import WheelCenter from '@/components/WheelCenter.vue';
import WheelShows from '@/components/WheelShows.vue';
import WheelWedges from '@/components/WheelWedges.vue';

export default {
	name: 'TheWheel',
	components: {
		WheelCenter,
		WheelShows,
		WheelWedges,
	},
	data() {
		return {
			hoveredShow: null,
			mouseOverRotateButton: false,
			shuffledShows: null,
			totalWedges: 16,
			visibleShows: [],
			visibleShowsFirstIndex: 0,
			visibleShowsLastIndex: null,
			wheelOffset: 0,
			wheelRotation: 0,
			wheelRotationCheckInterval: null,
			wheelStateClass: 'pbs-v-wheel-before-enter',
			wheelTransitionDuration: null,
			windowWidth: window.innerWidth,
		};
	},
	props: {
		shows: Array,
	},
	created() {
		const data = this;

		data.wheelTransitionDuration =
			parseFloat(
				getComputedStyle(document.documentElement).getPropertyValue(
					'--pbs-wheel-transition-duration'
				)
			) * 1000;

		data.shuffledShows = data.shuffleShows(data.shows);
		data.shuffledShows = data.shows;

		data.visibleShows = data.shuffledShows.slice(
			0,
			data.totalWedges / 2 + 5
		);

		data.visibleShowsLastIndex = data.totalWedges / 2;

		data.wheelOffset =
			((data.shuffledShows.length % data.totalWedges) * 360) /
			data.totalWedges;

		window.addEventListener('resize', () => {
			data.windowWidth = window.innerWidth;
		});
	},
	mounted() {
		const data = this;

		const mediaQuery = window.matchMedia(
			'(prefers-reduced-motion: reduce)'
		);
		if (mediaQuery.matches) {
			data.wheelRotation = -45;
		} else {
			data.wheelRotation = -90;
		}

		setTimeout(() => {
			data.wheelRotation = 0;
			data.wheelStateClass = 'pbs-v-wheel-enter';
		}, data.wheelTransitionDuration);

		setTimeout(() => {
			data.visibleShows = data.shuffledShows.slice(
				0,
				data.totalWedges / 2 + 1
			);
		}, data.wheelTransitionDuration * 2);
	},
	computed: {
		wheelMarginBottom() {
			let wheelMarginBottom = (this.windowWidth / 4) * -1;

			if (this.windowWidth > 1200) {
				wheelMarginBottom = -300;
			}

			return wheelMarginBottom;
		},
	},
	methods: {
		enterLeftRotate() {
			const data = this;

			data.mouseOverRotateButton = true;
			data.shiftShowsClockwise();

			data.wheelRotationCheckInterval = setInterval(() => {
				data.shiftShowsClockwise();
			}, data.wheelTransitionDuration + 50);
		},
		enterRightRotate() {
			const data = this;

			data.mouseOverRotateButton = true;
			data.shiftShowsCounterClockwise();

			data.wheelRotationCheckInterval = setInterval(() => {
				data.shiftShowsCounterClockwise();
			}, data.wheelTransitionDuration + 50);
		},
		focusOrHoverShow({ show }) {
			this.hoveredShow = show;
		},
		leaveLeftRotate() {
			this.mouseOverRotateButton = false;
			clearInterval(this.wheelRotationCheckInterval);
		},
		leaveRightRotate() {
			this.mouseOverRotateButton = false;
			clearInterval(this.wheelRotationCheckInterval);
		},
		shiftShowsClockwise() {
			const data = this;

			data.wheelRotation += 360 / data.totalWedges;

			let previousShow =
				data.shuffledShows[data.visibleShowsFirstIndex - 1];

			if (data.shuffledShows[data.visibleShowsFirstIndex - 1]) {
				data.visibleShowsFirstIndex -= 1;
				previousShow.revolutions =
					data.shuffledShows[
						data.visibleShowsFirstIndex + 1
					].revolutions;
			} else {
				previousShow =
					data.shuffledShows[data.shuffledShows.length - 1];
				data.visibleShowsFirstIndex = data.shuffledShows.length - 1;
				previousShow.revolutions =
					data.shuffledShows[0].revolutions - 1;
			}

			data.visibleShowsLastIndex -= 1;
			if (data.visibleShowsLastIndex < 0) {
				data.visibleShowsLastIndex = data.shuffledShows.length - 1;
			}

			previousShow.offset = previousShow.revolutions * data.wheelOffset;

			data.visibleShows.unshift(previousShow);

			setTimeout(() => {
				data.visibleShows.pop();
			}, data.wheelTransitionDuration);
		},
		shiftShowsCounterClockwise() {
			const data = this;

			data.wheelRotation -= 360 / data.totalWedges;

			let nextShow = data.shuffledShows[data.visibleShowsLastIndex + 1];

			if (data.shuffledShows[data.visibleShowsLastIndex + 1]) {
				data.visibleShowsLastIndex += 1;
				nextShow.revolutions =
					data.shuffledShows[
						data.visibleShowsLastIndex - 1
					].revolutions;
			} else {
				nextShow = data.shuffledShows[0];
				data.visibleShowsLastIndex = 0;
				nextShow.revolutions =
					data.shuffledShows[data.shuffledShows.length - 1]
						.revolutions + 1;
			}

			data.visibleShowsFirstIndex += 1;
			if (data.visibleShowsFirstIndex > data.shuffledShows.length - 1) {
				data.visibleShowsFirstIndex = 0;
			}

			nextShow.offset = nextShow.revolutions * data.wheelOffset;

			data.visibleShows.push(nextShow);

			setTimeout(() => {
				data.visibleShows.shift();
			}, data.wheelTransitionDuration);
		},
		shuffleShows(shows) {
			let currentIndex = shows.length,
				randomIndex;

			while (currentIndex != 0) {
				randomIndex = Math.floor(Math.random() * currentIndex);
				currentIndex--;

				[shows[currentIndex], shows[randomIndex]] = [
					shows[randomIndex],
					shows[currentIndex],
				];
			}

			return shows;
		},
	},
};
</script>

<style lang="scss" scoped>
.pbs-c-wheel {
	aspect-ratio: 1 / 1;
	margin-block-start: 5%;
	margin-inline: auto;
	max-width: 600px;
	position: relative;
	transform-origin: 50% 50%;
	transition-property: opacity, transform;
	width: 50%;

	&.pbs-v-wheel-before-enter {
		transform: scale(0);
		transition-duration: 3s;
	}

	&.pbs-v-wheel-enter {
		transform: scale(1);
		transition-duration: var(--pbs-wheel-transition-duration);
	}
}

.pbs-c-wheel:hover {
	transform: scale(1.2);
}

.pbs-c-wheel-container {
	border-radius: 50%;
	height: 100%;
	left: 0;
	overflow: hidden;
	position: absolute;
	top: 0;
	width: 100%;
	z-index: 100;
}

.pbs-c-wheel-shows {
	border-radius: 50%;
	height: 100%;
	left: 0;
	overflow: hidden;
	position: absolute;
	top: 0;
	transform-origin: 50% 50%;
	transition-duration: var(--pbs-wheel-transition-duration);
	transition-timing-function: ease-in-out;
	width: 100%;
}

.pbs-c-rotate-wheel {
	aspect-ratio: 1 / 1;
	background-color: var(--pbs-green-300);
	border-radius: 9999px;
	border: none;
	cursor: pointer;
	padding: 0;
	position: absolute;
	top: 50%;
	transform: translate(0, -50%);
	transform-origin: 0 100%;
	transition-duration: 0.35s;
	width: 25%;
	z-index: 50;
}

.pbs-c-rotate-wheel::before {
	background-color: white;
	border-radius: 50%;
	content: '';
	height: 75%;
	left: 50%;
	position: absolute;
	top: 50%;
	transform: translate(-50%, -50%);
	width: 75%;
	z-index: 0;
}

.pbs-c-rotate-wheel::after {
	background-color: var(--pbs-yellow-400);
	border-radius: 50%;
	content: '';
	height: 65%;
	left: 50%;
	position: absolute;
	top: 50%;
	transform: translate(-50%, -50%);
	width: 65%;
	z-index: 100;
}

.pbs-c-rotate-arrow {
	height: 50%;
	left: 50%;
	position: absolute;
	top: 50%;
	transition-duration: var(--pbs-wheel-transition-duration);
	transition-property: height, width;
	width: 50%;
	z-index: 200;
}

.pbs-c-rotate-wheel:hover {
	&::after {
		filter: brightness(105%);
	}

	.pbs-c-rotate-arrow {
		height: 45%;
		width: 45%;
	}
}

.pbs-v-rotate-arrow-left {
	transform: translate(-60%, -50%) scaleX(-1) scaleY(-1);
}

.pbs-v-rotate-arrow-right {
	transform: translate(-40%, -50%) scaleY(-1);
}

.pbs-v-rotate-wheel-left {
	left: 0;
	right: auto;
}

.pbs-v-rotate-wheel-right {
	left: auto;
	right: 0;
}

.pbs-c-wheel-all-shows {
	border-radius: 50%;
	left: 0;
	height: 100%;
	position: absolute;
	top: 0;
	transform-origin: 50% 50%;
	transform: scale(0) rotate(52deg);
	transition-duration: 0.5s;
	width: 100%;

	svg {
		left: 50%;
		position: absolute;
		top: -7%;
		transform: translate(-50%, 0);
		width: 37.2123%;
	}
}

.pbs-c-wheel-all-shows-background {
	fill: var(--pbs-yellow-400);
	transition-duration: 0.25s;
	transition-property: fill;
}

.pbs-c-wheel-all-shows-text {
	fill: var(--pbs-orange-400);
	transition-duration: 0.25s;
	transition-property: fill;
}

.pbs-c-wheel-all-shows:hover,
.pbs-c-wheel-all-shows a:focus {
	.pbs-c-wheel-all-shows-background {
		fill: var(--pbs-green-200);
	}

	.pbs-c-wheel-all-shows-text {
		fill: white;
	}
}

.pbs-c-wheel:hover,
.pbs-c-wheel:focus-within {
	.pbs-v-rotate-wheel-left {
		transform: translate(-67.5%, -77.5%);
	}

	.pbs-v-rotate-wheel-right {
		transform: translate(67.5%, -77.5%);
	}

	.pbs-c-wheel-all-shows {
		opacity: 1;
		transform: scale(0.99) rotate(52deg);
	}
}

@media (min-width: 1200px) {
	.pbs-c-wheel {
		margin-block-start: 60px;
	}
}

@media (prefers-reduced-motion) {
	.pbs-c-wheel {
		&.pbs-v-wheel-before-enter {
			opacity: 0;
			transform: scale(1);
		}

		&.pbs-v-wheel-enter {
			opacity: 1;
			transform: scale(1);
		}
	}

	.pbs-c-wheel:hover {
		transform: scale(1);
	}
}
</style>
