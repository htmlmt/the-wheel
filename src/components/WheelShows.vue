<template>
	<nav>
		<ul>
			<li
				v-for="(show, index) in shuffledShows"
				:class="!visibleShows.includes(show) ? 'pbs-u-sr-only' : ''"
				:key="show.id"
				:style="{
					rotate: visibleShows.includes(show)
						? `${(360 / totalWedges) * index - 90 + show.offset}deg`
						: null,
					width: visibleShows.includes(show)
						? (2 * Math.PI * 500) / totalWedges / 10 + '%'
						: null,
				}"
			>
				<a
					:href="show.href"
					@focus="$emit('focus-or-hover-show', { show: show })"
					@blur="$emit('focus-or-hover-show', { show: null })"
					@mouseenter="$emit('focus-or-hover-show', { show: show })"
					@mouseleave="$emit('focus-or-hover-show', { show: null })"
				>
					<picture>
						<source :srcset="show.images.avif" type="image/avif" />
						<img :alt="show.title" :src="show.images.png" />
					</picture>
				</a>
			</li>
		</ul>
	</nav>
</template>

<script>
export default {
	name: 'WheelShow',
	props: {
		shuffledShows: {
			type: Array,
		},
		totalWedges: {
			type: Number,
		},
		visibleShows: {
			type: Array,
		},
	},
};
</script>

<style lang="scss" scoped>
nav {
	border-radius: 50%;
	height: 100%;
	left: 0;
	overflow: hidden;
	position: absolute;
	top: 0;
	width: 100%;
}

ul {
	list-style-type: none;
	margin: 0;
	padding: 0;
}

li {
	align-items: flex-start;
	display: flex;
	height: 50%;
	justify-content: center;
	left: 50%;
	position: absolute;
	top: 0;
	transform-origin: 0% 100%;
	transform: translate(-50%, 0);
}

a {
	margin-block-start: 20%;
	transition-duration: 0.25s;
	transition-property: transform;
	width: 60%;

	&:hover {
		transform: scale(1.1);
	}
}

img {
	aspect-ratio: 1 / 1;
	display: block;
	width: 100%;
}
</style>
