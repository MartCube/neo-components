<template>
	<div class="neo_slider">
		<h2 class="title">See how we can help you by adjusting the sliders below:</h2>

		<p>What stage are you at in the brand lifecycle?</p>

		<vue-slider width="300px" height="7px" :data="sliderData" class="slider" :process-style="{ backgroundColor: '#e8b21a' }" :tooltip-style="{ backgroundColor: '#e8b21a', borderColor: '#e8b21a' }">
			<template v-slot:dot>
				<div class="custom_dot"></div>
			</template>
		</vue-slider>

		<NeoBtn>Next Step</NeoBtn>
	</div>
</template>

<script>
export default {
	props: {},
	data: () => ({
		sliderData: ['Pre-launch', 'Second-step', 'third-step', 'final-step'],
	}),
}
</script>

<style lang="scss" scoped>
.neo_slider {
	width: 500px;
	margin: 20px;
	padding: 40px;
	border-radius: 20px;
	box-shadow: 0px 0px 9px 0px rgba(0, 0, 0, 0.1);

	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: flex-start;

	.slider {
		margin: 40px 0;
		.custom_dot {
			position: absolute;
			top: -7px;
			left: -7px;

			width: 28px;
			height: 28px;
			border-radius: 50%;
			background: #e8b21a;
		}
	}

	.title {
		margin: 20px 0;
		color: #666;
	}
	p {
		color: #333;
		width: 50%;
	}
	.neo_btn {
		align-self: flex-end;
	}
}
</style>
