<template>
	<svg viewBox="0 0 1000 1000" xmlns="http://www.w3.org/2000/svg">
		<circle cx="500" cy="500" fill="var(--pbs-green-300)" r="500" />

		<g>
			<circle cx="500" cy="500" fill="var(--pbs-green-100)" r="500" />

			<path
				d="M500,500,84.84,222.6C123.14,165.28,162,126.08,219,87.28Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500,10.29,597.41C-3.16,529.79-3.4,474.6,9.45,406.87Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500,222.6,915.16C165.28,876.86,126.08,838,87.28,781Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500l97.41,489.71c-67.62,13.45-122.81,13.69-190.54.84Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500,915.16,777.4C876.86,834.72,838,873.92,781,912.72Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500l489.71-97.41c13.45,67.62,13.69,122.81.84,190.54Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500,777.4,84.84C834.72,123.14,873.92,162,912.72,219Z"
				fill="var(--pbs-green-200)"
			/>
			<path
				d="M500,500,402.59,10.29C470.21-3.16,525.4-3.4,593.13,9.45Z"
				fill="var(--pbs-green-200)"
			/>
		</g>

		<path
			d="M500,0C223.86,0,0,223.86,0,500s223.86,500,500,500,500-223.86,500-500S776.14,0,500,0Zm0,975C237.66,975,25,762.34,25,500S237.66,25,500,25,975,237.66,975,500,762.34,975,500,975Z"
			fill="var(--pbs-green-300)"
		/>

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
