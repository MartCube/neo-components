<template>
	<div class="footer">
		<div class="links">
			<h2>Quick Links</h2>
			<n-link to="/"> Team</n-link>
			<n-link to="/"> Services</n-link>
			<n-link to="/"> NeoHealthHub</n-link>
			<n-link to="/"> NeoNavitas</n-link>
			<n-link to="/"> NeoOptima</n-link>
			<n-link to="/"> NeoX</n-link>
		</div>
		<div class="resources">
			<h2>Resources</h2>
			<n-link to="/"> Case Studies</n-link>
			<n-link to="/"> Articles</n-link>
			<n-link to="/"> White Papers</n-link>
		</div>
		<div class="contact">
			<h2>Get in touch</h2>
			<n-link to="/"> +44 (0) 1455 371323</n-link>
			<n-link to="/"> mail@neosypher.com</n-link>
		</div>
		<div class="terms">
			<p>© NeoSypher Limited 2020, All Rights Reserved. Registered in the UK. No. 09544979. Unit 8, St John’s Business Park, Rugby Road, Lutterworth, Leicestershire, LE17 4HB. Terms | Privacy Policy</p>
		</div>
		<div class="logos">
			<img src="/logos/neoSypher.png" alt="neoSypher" />
			<img src="/logos/platinum.png" alt="neoSypher" />
		</div>
	</div>
</template>

<style lang="scss" scoped>
.footer {
	display: flex;
	justify-content: flex-start;
	flex-wrap: wrap;

	padding: 0 5%;
	background: #e01c5c;

	.links,
	.resources,
	.contact {
		margin: 5%;
		display: flex;
		flex-direction: column;

		h2 {
			color: white;
			margin-bottom: 40px;
		}
		a {
			text-decoration: none;
			color: white;
			margin: 10px 0;
		}
	}
	.terms {
		margin: 0 5%;
		color: white;
		font-size: 11px;
	}
	.logos {
		margin: 5%;
		img {
			margin-right: 20px;
		}
	}
}
</style>
