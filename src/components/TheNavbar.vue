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
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="10"
						height="7"
					>
						<path
							class="arrow"
							fill="none"
							stroke="#FFF"
							stroke-width="2"
							opacity=".75"
							d="M1 1l4 4 4-4"
						/>
					</svg>

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
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="10"
						height="7"
					>
						<path
							class="arrow"
							fill="none"
							stroke="#FFF"
							stroke-width="2"
							opacity=".75"
							d="M1 1l4 4 4-4"
						/>
					</svg>
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
					<svg
						xmlns="http://www.w3.org/2000/svg"
						width="10"
						height="7"
					>
						<path
							class="arrow"
							fill="none"
							stroke="#FFF"
							stroke-width="2"
							opacity=".75"
							d="M1 1l4 4 4-4"
						/>
					</svg>
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
			border-radius: 5px;
			transform: translateX(-50%);
			box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.3);
			text-align: center;
		}
		@include breakpoint(mobile) {
			top: 10rem;
		}
		.nav-right {
			@include breakpoint(tablet-land) {
				border-top: 1px solid $footer-text-color;
				width: 80%;
				margin-top: 1rem;
                padding: 2rem 0 1rem;
			}
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
				display: block;
				color: $body-copy-color;
			}
			@include breakpoint(mobile) {
				font-size: 1.8rem;
			}
			&:hover {
				color: #fff;
				@include breakpoint(tablet-land) {
					color: $footer-text-color;
				}
				&:after {
					width: 100%;
					background-color: #fff;
				}
				svg {
					transform: rotate(180deg);
					@include breakpoint(tablet-land) {
						transform: none;
					}
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
			svg {
				transition: transform 0.3s;
				margin: 0 0 2px 4px;
				path {
					@include breakpoint(tablet-land) {
						stroke: $cta-text-color;
					}
				}
			}
			.drop-menu {
				position: absolute;
				left: -1rem;
				width: 13rem;
				top: 3rem;
				background-color: #fff;
				padding: 1rem 2rem 1.5rem;
				border-radius: 2rem;
				box-shadow: 0 0.5rem 0.5rem
					darken(rgba(255, 122, 133, 0.3), 40%);
				transform: scaleY(0);
				will-change: transform;
				transform-origin: top;
				transition: transform 0.3s;
				@include breakpoint(tablet-land) {
					position: static;
					z-index: 10;
					transform: scaleY(1);
					box-shadow: none;
				}
				&__item {
					display: block;
					padding: 0.75rem 0;
					color: lighten($body-copy-color, 20%);
					font-weight: 500;
					font-size: 1.4rem;
					transition: color 0.3s, text-shadow 0.3s;
					@include breakpoint(tablet-land) {
						padding: 1.25rem 0;
                        font-size: 1.6rem;
					}
					&:hover {
						color: $cta-hover-bg-color;
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
			margin: 0 auto;
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