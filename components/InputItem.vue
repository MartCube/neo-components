<template>
	<ValidationProvider v-slot="{ errors, classes }" :rules="rules" :mode="mode" tag="div" class="input_item">
		<label :for="name">{{ label }}</label>
		<span class="error" :class="classes"> {{ errors[0] }} </span>

		<input v-model="input_value" type="text" :name="name" :placeholder="placeholder" />
	</ValidationProvider>
</template>

<script>
import { ValidationProvider } from 'vee-validate'
export default {
	components: {
		ValidationProvider,
	},
	props: {
		name: {
			type: String,
			required: true,
		},
		label: {
			type: String,
			required: true,
		},
		placeholder: {
			type: String,
			required: true,
		},
		rules: {
			type: String,
			default: 'required',
		},
		mode: {
			type: String,
			default: 'eager',
		},
	},
	data: () => ({
		input_value: '',
	}),
}
</script>

<style lang="scss" scoped>
.input_item {
	width: 100%;
	margin: 20px 0;
	position: relative;

	display: flex;
	flex-direction: column;
	flex-wrap: wrap;
	label {
		font-size: 0.8em;

		margin-bottom: 10px;
		margin-left: 25px;
	}
	.error {
		position: absolute;
		top: 0;
		right: 25px;
		font-size: 0.8em;
		color: #ff1461;

		display: none;
		&.invalid {
			display: flex;
		}
	}
	input {
		width: 100%;
		padding: 15px 25px;
		border: 1px solid #cdcdcd;
		border-radius: 33px;
		resize: none;
		font-size: 1em;
		&:focus {
			outline: none;
			box-shadow: (0 0 5px rgba(74, 194, 240, 1));
			border: 1px solid #4ac2f0;
		}
	}
}
</style>
