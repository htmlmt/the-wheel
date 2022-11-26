<template>
	<svg viewBox="0 0 1000 1000" xmlns="http://www.w3.org/2000/svg">
		<g>
			<circle cx="500" cy="500" fill="var(--pbs-green-100)" r="500" />

			<path
				fill="var(--pbs-green-200)"
				d="M500,500,84.84,222.6C123.14,165.28,162,126.08,219,87.28Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500,10.29,597.41C-3.16,529.79-3.4,474.6,9.45,406.87Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500,222.6,915.16C165.28,876.86,126.08,838,87.28,781Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500l97.41,489.71c-67.62,13.45-122.81,13.69-190.54.84Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500,915.16,777.4C876.86,834.72,838,873.92,781,912.72Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500l489.71-97.41c13.45,67.62,13.69,122.81.84,190.54Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500,777.4,84.84C834.72,123.14,873.92,162,912.72,219Z"
			/>
			<path
				fill="var(--pbs-green-200)"
				d="M500,500,402.59,10.29C470.21-3.16,525.4-3.4,593.13,9.45Z"
			/>
		</g>

		<circle cx="500" cy="500" fill="white" r="275" />

		<circle cx="500" cy="500" fill="var(--pbs-yellow-400)" r="250" />
	</svg>
</template>

<script>
export default {
	name: 'WheelWedges',
	props: {
		totalWedges: {
			type: Number,
		},
	},
};
</script>

<style lang="scss" scoped>
svg {
	background-color: var(--pbs-green-300);
	border: 1.25vw solid transparent;
	border-radius: 50%;
	box-sizing: content-box;
}
</style>
