<template>
	<div class="container">
		<h2>Neo Components</h2>

		<ValidationObserver ref="contact_form" tag="form" class="form" @submit.prevent="Submit()">
			<h4>form and InputItem</h4>
			<InputItem name="name" label="Your name*" placeholder="John Doe" @getValue="getName" />
			<InputItem name="email" label="Contact email*" placeholder="you@example.com" :rules="'email|required'" @getValue="getEmail" />

			<NeoBtn type="submit">Send Message</NeoBtn>
		</ValidationObserver>

		<div class="white_papper_list">
			<WhitePapper :data="whitePapperData" />
			<WhitePapper :data="whitePapperData" />
		</div>
		<div class="article_list">
			<Article :data="article" />
			<Article :data="article" />
		</div>
		<NeoSlider />
	</div>
</template>

<script>
import { ValidationObserver } from 'vee-validate'

export default {
	components: {
		ValidationObserver,
	},
	data: () => ({
		form: {
			name: String,
			email: String,
		},
		whitePapperData: {
			title: 'White Papper Title',
			text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur quia cum labore esse! A, quisquam repellendus tenetur ex repudiandae earum.',
			tags: [
				{
					value: 'neoTag1',
					color: '#e01c5c',
				},
				{
					value: 'neoTag2',
					color: '#3f8ef2',
				},
				{
					value: 'neoTag3',
					color: '#3BB078',
				},
			],
			authors: [
				{
					name: 'Jane Wow',
					image: '/images/author1.png',
				},
				{
					name: 'Jown Doe',
					image: '/images/author2.png',
				},
				{
					name: 'Joe Bow',
					image: '/images/author3.png',
				},
			],
		},
		article: {
			mainImage: '/images/article1.png',
			title: 'Article Title 1',
			author: {
				name: 'Jane Wow',
				image: '/images/author1.png',
			},
			date: '22/10/2020',
		},
	}),
	methods: {
		getName(value) {
			this.form.name = value
		},
		getEmail(value) {
			this.form.email = value
		},
		async Submit() {
			const isValid = await this.$refs.contact_form.validate()
			if (!isValid) return

			console.log('submit')
		},
	},
}
</script>

<style lang="scss" scoped>
h2 {
	margin-bottom: 10%;
}

.form {
	margin: 50px 0;

	h4 {
		margin: 20px 0;
	}
	width: 400px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}

.white_papper_list,
.article_list {
	margin: 50px 0;
	display: flex;
	justify-content: center;
	align-items: center;
}
</style>
