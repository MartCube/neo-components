<template>
	<div class="article">
		<img class="main_image" :src="data.mainImage" :alt="data.title" />
		<h2 class="title">{{ data.title }}</h2>

		<div class="author">
			<img :src="data.author.image" :alt="data.author.name" />
			<p>{{ data.author.name }}</p>
		</div>
		<NeoBtn>Read More</NeoBtn>
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
.article {
	width: 300px;
	margin: 20px;
	padding: 20px;
	border-radius: 20px;
	box-shadow: 0px 0px 9px 0px rgba(0, 0, 0, 0.1);

	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: flex-start;
	.main_image {
		width: 100%;
	}
	.title {
		margin: 20px 0;
	}
	.author {
		margin-bottom: 20px;

		display: flex;
		justify-content: center;
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
