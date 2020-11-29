<template>
	<div class="neo_tag" :style="{ background: color }">
		<span> {{ value }}</span>
	</div>
</template>

<script>
export default {
	props: {
		color: {
			type: String,
			default: '#e01c5c',
		},
		value: {
			type: String,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
.neo_tag {
	margin: 5px;
	padding: 5px 20px;
	border-radius: 20px;
	color: white;
	font-weight: 700;
}
</style>
