<template>
	<header class="header">
		<img
			src="@/assets/images/logo.svg"
			alt="Manage logo"
			class="logo"
		/>

		<nav
			v-if="showMobileMenu"
			class="nav"
		>
			<div class="nav-left">
				<a
					href="#"
					class="nav-item"
				>
					Product
					<img
						src="@/assets/images/icon-arrow-light.svg"
						class="arrow"
					/>

					<div class="drop-menu">
						<a
							href="#"
							class="drop-menu__item"
						>Overview</a>
						<a
							href="#"
							class="drop-menu__item"
						>Pricing</a>
						<a
							href="#"
							class="drop-menu__item"
						>Marketplace</a>
						<a
							href="#"
							class="drop-menu__item"
						>Features</a>
						<a
							href="#"
							class="drop-menu__item"
						>Integrations</a>
					</div>
				</a>

				<a
					href="#"
					class="nav-item"
				>
					Company
					<img
						src="@/assets/images/icon-arrow-light.svg"
						class="arrow"
					/>
					<div class="drop-menu">
						<a
							href="#"
							class="drop-menu__item"
						>About</a>
						<a
							href="#"
							class="drop-menu__item"
						>Team</a>
						<a
							href="#"
							class="drop-menu__item"
						>Blog</a>
						<a
							href="#"
							class="drop-menu__item"
						>Careers</a>
					</div>
				</a>

				<a
					href="#"
					class="nav-item"
				>
					Connect
					<img
						src="@/assets/images/icon-arrow-light.svg"
						class="arrow"
					/>
					<div class="drop-menu">
						<a
							href="#"
							class="drop-menu__item"
						>Contact</a>
						<a
							href="#"
							class="drop-menu__item"
						>Newsletter</a>
						<a
							href="#"
							class="drop-menu__item"
						>LinkedIn</a>
					</div>
				</a>
			</div>
			<div class="nav-right">
				<a
					href="#"
					class="nav-item"
				>Login</a>

				<AppButton>Sign Up</AppButton>
			</div>
		</nav>

		<img
			v-if="showMobileMenu"
			src="@/assets/images/icon-close.svg"
			alt="close mobile menu icon"
			@click="$emit('close')"
			class="mobileClose"
		/>
		<img
			v-else
			src="@/assets/images/icon-hamburger.svg"
			alt="mobile menu icon"
			@click="$emit('open')"
			class="hamburger"
		/>
	</header>
</template>

<script>
export default {
	name: "TheNavbar",
	props: {
		showMobileMenu: {
			type: Boolean,
		},
	},
};
</script>

<style lang="scss" scoped>
.header {
	position: absolute;
	z-index: 100;
	left: 0;
	right: 0;
	display: flex;
	align-items: center;
	min-height: 10em;
	width: 100%;
	@include breakpoint(tablet-land) {
		min-height: 10rem;
	}
	.logo {
		width: 15rem;
		margin-right: 5rem;
		@include breakpoint(tablet-port) {
			width: 10rem;
		}
		@include breakpoint(mobile-small) {
			width: 8rem;
		}
	}
	.nav {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		@include breakpoint(tablet-land) {
			position: absolute;
			display: flex;
			flex-direction: column;
			background-color: #fff;
			width: 85%;
			top: 12rem;
			padding: 4rem 2rem;
			left: 50%;
			transform: translateX(-50%);
			box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.3);
			text-align: center;
		}
		@include breakpoint(mobile) {
			top: 10rem;
		}
		.nav-item {
			position: relative;
			margin: 0 1.85rem;
			padding-bottom: 1rem;
			font-size: 1.8rem;
			font-weight: 500;
			color: darken(#fff, 10%);
			transition: color 0.3s;

			@include breakpoint(tablet-land) {
				margin: 0;
				padding: 1.5rem 0;
				font-weight: 600;
				font-size: 2.3rem;
			}
			@include breakpoint(mobile) {
				font-size: 1.8rem;
			}
			&:hover {
				color: #fff;
				&:after {
					width: 100%;
					background-color: #fff;
				}
				img {
					transform: rotate(180deg);
				}
				.drop-menu {
					transform: scaleY(1);
				}
			}
			&:after {
				position: absolute;
				bottom: 7px;
				left: 50%;
				transform: translateX(-50%);
				width: 0;
				content: "";
				height: 1px;
				background-color: transparent;
				transition: width 0.3s, background-color 0.3s;
			}
			.arrow {
				margin-left: 0.5rem;
			}
			img {
				transition: transform 0.3s;
				margin-bottom: 2px;
			}
			.drop-menu {
				position: absolute;
				left: -2rem;
				width: 15rem;
				top: 3rem;
				background-color: #fff;
				padding: 1rem 2rem;
				border-radius: 5px;
				box-shadow: 0 0.5rem 0.5rem
					darken(rgba(255, 122, 133, 0.3), 40%);
				transform: scaleY(0);
				transform-origin: top;
				transition: transform 0.3s;
				&__item {
					display: block;
					padding: 0.75rem 0;
					color: lighten($body-copy-color, 20%);
					font-weight: 300;
					font-size: 1.6rem;
					transition: color 0.3s, text-shadow 0.3s;
					&:hover {
						color: $cta-hover-bg-color;
						text-shadow: 0.5px 0.5px 0.5px $cta-hover-bg-color;
					}
				}
			}
		}
	}
	button {
		margin-left: auto;
		@include breakpoint(laptop) {
			display: none;
		}
		@include breakpoint(tablet-land) {
			display: block;
			color: #fff;
			background: $hero-bg-gradient;
			border: none;
		}
	}
	.hamburger {
		display: none;
		margin-left: auto;
		@include breakpoint(ipadPro) {
			display: block;
		}
	}
	.mobileClose {
		margin-left: auto;
		@media screen and (min-width: 769px) {
			display: none;
		}
	}
}
</style>