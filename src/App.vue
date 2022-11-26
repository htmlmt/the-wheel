<template>
	<TheWheel :shows="shows" />

	<div class="pbs-c-games"></div>
</template>

<script>
import TheWheel from './components/TheWheel.vue';

export default {
	name: 'App',
	components: {
		TheWheel,
	},
	data() {
		return {
			shows: [
				{
					href: 'https://pbskids.org/almasway',
					id: 1,
					images: {
						avif: require('./assets/almas-way.avif'),
						png: require('./assets/almas-way.png'),
					},
					offset: 0,
					revolutions: 0,
					title: "Alma's Way",
				},
				{
					href: 'https://pbskids.org/arthur',
					id: 2,
					images: {
						avif: require('./assets/arthur.avif'),
						png: require('./assets/arthur.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Arthur',
				},
				{
					href: 'https://pbskids.org/clifford/',
					id: 3,
					images: {
						avif: require('./assets/clifford-the-big-red-dog.avif'),
						png: require('./assets/clifford-the-big-red-dog.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Clifford the Big Red Dog',
				},
				{
					href: 'https://pbskids.org/curiousgeorge/',
					id: 4,
					images: {
						avif: require('./assets/curious-george.avif'),
						png: require('./assets/curious-george.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Curious George',
				},
				{
					href: 'https://pbskids.org/cyberchase/',
					id: 5,
					images: {
						avif: require('./assets/cyberchase.avif'),
						png: require('./assets/cyberchase.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Cyberchase',
				},
				{
					href: 'https://pbskids.org/daniel/',
					id: 6,
					images: {
						avif: require('./assets/daniel-tigers-neighborhood.avif'),
						png: require('./assets/daniel-tigers-neighborhood.png'),
					},
					offset: 0,
					revolutions: 0,
					title: "Daniel Tiger's Neighborhood",
				},
				{
					href: 'https://pbskids.org/designsquad/',
					id: 7,
					images: {
						avif: require('./assets/design-squad.avif'),
						png: require('./assets/design-squad.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Design Squad',
				},
				{
					href: 'https://pbskids.org/dinosaurtrain/',
					id: 8,
					images: {
						avif: require('./assets/dinosaur-train.avif'),
						png: require('./assets/dinosaur-train.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Dinosaur Train',
				},
				{
					href: 'https://pbskids.org/donkeyhodie',
					id: 9,
					images: {
						avif: require('./assets/donkey-hodie.avif'),
						png: require('./assets/donkey-hodie.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Donkey Hodie',
				},
				{
					href: 'https://pbskids.org/elinor',
					id: 10,
					images: {
						avif: require('./assets/elinor-wonders-why.avif'),
						png: require('./assets/elinor-wonders-why.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Elinor Wonders Why',
				},
				{
					href: 'https://pbskids.org/heroelementary',
					id: 11,
					images: {
						avif: require('./assets/hero-elementary.avif'),
						png: require('./assets/hero-elementary.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Hero Elementary',
				},
				{
					href: 'https://pbskids.org/jellybenandpogo',
					id: 12,
					images: {
						avif: require('./assets/jelly-ben-and-pogo.avif'),
						png: require('./assets/jelly-ben-and-pogo.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Jelly, Ben & Pogo',
				},
				{
					href: 'https://pbskids.org/luna',
					id: 13,
					images: {
						avif: require('./assets/lets-go-luna.avif'),
						png: require('./assets/lets-go-luna.png'),
					},
					offset: 0,
					revolutions: 0,
					title: "Let's Go Luna",
				},
				{
					href: 'https://pbskids.org/martha/',
					id: 14,
					images: {
						avif: require('./assets/martha-speaks.avif'),
						png: require('./assets/martha-speaks.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Martha Speaks',
				},
				{
					href: 'https://pbskids.org/molly',
					id: 15,
					images: {
						avif: require('./assets/molly-of-denali.avif'),
						png: require('./assets/molly-of-denali.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Molly of Denali',
				},
				{
					href: 'https://pbskids.org/naturecat/',
					id: 16,
					images: {
						avif: require('./assets/nature-cat.avif'),
						png: require('./assets/nature-cat.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Nature Cat',
				},
				{
					href: 'https://pbskids.org/oddsquad',
					id: 17,
					images: {
						avif: require('./assets/odd-squad.avif'),
						png: require('./assets/odd-squad.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Odd Squad',
				},
				{
					href: 'https://pbskids.org/noah/',
					id: 18,
					images: {
						avif: require('./assets/oh-noah.avif'),
						png: require('./assets/oh-noah.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Oh Noah!',
				},
				{
					href: 'https://pbskids.org/peg/',
					id: 19,
					images: {
						avif: require('./assets/peg-and-cat.avif'),
						png: require('./assets/peg-and-cat.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Peg + Cat',
				},
				{
					href: 'https://pbskids.org/pinkalicious',
					id: 20,
					images: {
						avif: require('./assets/pinkalicious-and-peterrific.avif'),
						png: require('./assets/pinkalicious-and-peterrific.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Pinkalicious and Peterrific',
				},
				{
					href: 'https://pbskids.org/plumlanding/',
					id: 21,
					images: {
						avif: require('./assets/plum-landing.avif'),
						png: require('./assets/plum-landing.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Plum Landing',
				},
				{
					href: 'https://pbskids.org/readyjetgo/',
					id: 22,
					images: {
						avif: require('./assets/ready-jet-go.avif'),
						png: require('./assets/ready-jet-go.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Ready Jet Go!',
				},
				{
					href: 'https://pbskids.org/rosiesrules',
					id: 23,
					images: {
						avif: require('./assets/rosies-rules.avif'),
						png: require('./assets/rosies-rules.png'),
					},
					offset: 0,
					revolutions: 0,
					title: "Rosie's Rules",
				},
				{
					href: 'https://pbskids.org/scigirls/',
					id: 24,
					images: {
						avif: require('./assets/scigirls.avif'),
						png: require('./assets/scigirls.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'SciGirls',
				},
				{
					href: 'https://pbskids.org/scribblesandink',
					id: 25,
					images: {
						avif: require('./assets/scribbles-and-ink.avif'),
						png: require('./assets/scribbles-and-ink.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Scribbles and Ink',
				},
				{
					href: 'https://pbskids.org/sesame/',
					id: 26,
					images: {
						avif: require('./assets/sesame-street.avif'),
						png: require('./assets/sesame-street.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Sesame Street',
				},
				{
					href: 'https://pbskids.org/sid/',
					id: 27,
					images: {
						avif: require('./assets/sid-the-science-kid.avif'),
						png: require('./assets/sid-the-science-kid.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Sid the Science Kid',
				},
				{
					href: 'https://pbskids.org/splashandbubbles',
					id: 28,
					images: {
						avif: require('./assets/splash-and-bubbles.avif'),
						png: require('./assets/splash-and-bubbles.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Splash and Bubbles',
				},
				{
					href: 'https://pbskids.org/superwhy/',
					id: 29,
					images: {
						avif: require('./assets/super-why.avif'),
						png: require('./assets/super-why.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Super Why!',
				},
				{
					href: 'https://pbskids.org/ruff/',
					id: 30,
					images: {
						avif: require('./assets/team-hamster-and-ruff-ruffman.avif'),
						png: require('./assets/team-hamster-and-ruff-ruffman.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Team Hamster! & Ruff Ruffman',
				},
				{
					href: 'https://pbskids.org/catinthehat/',
					id: 31,
					images: {
						avif: require('./assets/the-cat-in-the-hat.avif'),
						png: require('./assets/the-cat-in-the-hat.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'The Cat in the Hat',
				},
				{
					href: 'https://pbskids.org/wildkratts/',
					id: 32,
					images: {
						avif: require('./assets/wild-kratts.avif'),
						png: require('./assets/wild-kratts.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Wild Kratts',
				},
				{
					href: 'https://pbskids.org/wordgirl/',
					id: 33,
					images: {
						avif: require('./assets/wordgirl.avif'),
						png: require('./assets/wordgirl.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'WordGirl',
				},
				{
					href: 'https://pbskids.org/xavier',
					id: 34,
					images: {
						avif: require('./assets/xavier-riddle-and-the-secret-museum.avif'),
						png: require('./assets/xavier-riddle-and-the-secret-museum.png'),
					},
					offset: 0,
					revolutions: 0,
					title: 'Xavier Riddle and the Secret Museum',
				},
			],
		};
	},
};
</script>

<style>
:root {
	--pbs-green-50: #a6ef18;
	--pbs-green-100: #adeb00;
	--pbs-green-200: #98d800;
	--pbs-green-300: #75c700;
	--pbs-orange-400: #f79200;
	--pbs-yellow-400: #ffe000;

	--pbs-wheel-transition-duration: 0.5s;
}

body {
	font-family: 'PBS_KIDS_Headline', sans-serif;
	margin: 0;
}

* {
	box-sizing: border-box;
}

.pbs-c-games {
	background-color: var(--pbs-green-50);
	height: 1000px;
	position: relative;
	z-index: 100;
}

.pbs-u-hidden {
	display: none;
}

.pbs-u-sr-only {
	border: 0;
	clip: rect(0 0 0 0);
	height: 1px;
	margin: -1px;
	overflow: hidden;
	padding: 0;
	position: absolute;
	width: 1px;
}
</style>
