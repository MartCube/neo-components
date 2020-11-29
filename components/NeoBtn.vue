<template>
	<button class="neo_btn" :class="{ fill: fill }" @click="handleClick">
		<template v-if="processing">
			<span>Processing...</span>
		</template>
		<template v-else>
			<slot></slot>
		</template>
	</button>
</template>

<script>
export default {
	name: 'NeoBtn',
	props: {
		processing: {
			type: Boolean,
		},
		fill: {
			type: Boolean,
		},
	},
	data: () => ({}),
	methods: {
		handleClick(e) {
			this.$emit('click', e)
		},
	},
}
</script>

<style lang="scss" scoped>
.neo_btn {
	padding: 0.75rem 2rem;
	box-shadow: 0px 0px 9px 0px rgba(0, 0, 0, 0.1);
	border: none;
	border-radius: 2rem;
	background: none;

	color: #3f8ef2;
	font-family: 'Comfortaa';
	font-weight: 700;
	cursor: pointer;

	&.fill {
		color: white;
		background: #3953d4;
	}

	&:focus {
		outline: none;
	}
}
</style>
