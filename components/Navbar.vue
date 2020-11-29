<template>
	<div class="navbar">
		<div class="logo">logo</div>
		<div class="links">
			<n-link to="/"> Services</n-link>
			<n-link to="/"> Case Studies</n-link>
			<n-link to="/"> Teams</n-link>
			<n-link to="/"> Resources</n-link>
		</div>
		<div class="menu">
			<NeoBtn fill>Contact Us</NeoBtn>
			<div class="menu_btn" @click="menuActive = !menuActive">
				<span class="circle"></span>
				<span class="circle"></span>
				<span class="circle"></span>
			</div>
		</div>
		<div v-if="menuActive" class="expansion">
			<div class="links">
				<n-link to="/"> Home</n-link>
				<n-link to="/"> Services</n-link>
				<n-link to="/"> NeoHealthHub</n-link>
				<n-link to="/"> Team</n-link>
				<n-link to="/"> Case Studies</n-link>
				<n-link to="/"> Contact</n-link>
			</div>
			<div class="terms">
				<h4>Terms &amp; Conditions | Privacy Policy</h4>
				<p>© NeoHealthHub Limited 2020, All Rights Reserved. NeoHealthHub Limited is Registered in the UK. No. 08351068, Unit 8, St John’s Business Park, Rugby Road, Lutterworth, Leicestershire, LE17 4HB</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Navbar',
	props: {},
	data: () => ({
		menuActive: false,
	}),
}
</script>

<style lang="scss" scoped>
.navbar {
	margin: 85px 0;
	display: flex;
	justify-content: space-around;
	align-items: center;

	.logo {
		z-index: 3;
	}
	.links {
		a {
			margin: 0 20px;
			text-decoration: none;
			color: #666;

			&:hover {
				color: #e01c5c;
			}
		}
	}
	.menu {
		display: flex;
		align-items: center;

		.menu_btn {
			z-index: 3;
			margin: 0 20px;
			cursor: pointer;
			display: flex;
			justify-content: center;
			align-items: center;
			.circle {
				width: 10px;
				height: 10px;
				margin: 2px;
				border-radius: 50%;
				background: #c3c3c4;
			}
		}
	}

	.expansion {
		z-index: 2;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100vh;
		background: #f3f3f3;

		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;

		.links {
			display: flex;
			flex-direction: column;
			a {
				margin: 20px 0;
				font-size: 2rem;
			}
		}
		.terms {
			position: fixed;
			bottom: 5%;
			right: 5%;

			width: 25%;
			color: #666;
			h4 {
				margin: 20px 0;
			}
			p {
				font-size: 11px;
			}
		}
	}
}

@media (max-width: 950px) {
	.navbar {
		.links {
			display: none;
		}
	}
}
</style>
