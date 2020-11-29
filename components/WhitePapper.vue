<template>
	<div class="white_papper">
		<h2 class="title">{{ data.title }}</h2>
		<!-- ask about text height-->
		<p class="text">{{ data.text }}</p>

		<div class="tags">
			<NeoTag v-for="tag in data.tags" :key="tag.value" :value="tag.value" :color="tag.color" />
		</div>
		<div class="authors">
			<img v-for="author in data.authors" :key="author.name" :src="author.image" :alt="author.name" />
			<p>Multiple authors</p>
		</div>
		<NeoBtn>Read Papper</NeoBtn>
	</div>
</template>

<script>
export default {
	props: {
		data: {
			type: Object,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
.white_papper {
	width: 400px;
	margin: 20px;
	padding: 20px;
	border-radius: 20px;
	box-shadow: 0px 0px 9px 0px rgba(0, 0, 0, 0.1);

	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: flex-start;

	.title {
		margin: 20px 0;
	}
	.tags {
		width: 100%;
		padding: 20px 0;

		display: flex;
		justify-content: flex-start;
		align-items: flex-start;
		flex-wrap: wrap;
	}
	.authors {
		padding: 20px 0;

		display: flex;
		justify-content: flex-start;
		align-items: center;
		img {
			width: 30px;
			height: 30px;
			border-radius: 30px;
			margin: 0 5px;
		}
		p {
			font-size: 0.8em;
			margin: 0 5px;
		}
	}
}
</style>
