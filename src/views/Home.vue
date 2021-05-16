<template>
	<div class="home">
		<section class="hero">
			<div class="overlay"></div>
			<div class="outer-container">
				<h1 class="hero-heading">A modern publishing platform</h1>
				<p class="subtext">
					Grow your audience and build your online brand
				</p>
				<div class="cta-container">
					<AppButton>Start For Free</AppButton>
					<AppButton :filled="false">Learn More</AppButton>
				</div>
			</div>
		</section>

		<section class="futuristicDesign">
			<div class="outer-container">
				<h2 class="section-heading">Designed for the future</h2>

				<div class="column-wrapper">
					<div class="col-1">
						<div class="info-block">
							<h3
								class="block-heading"
								data-aos="fade-right"
							>
								Introducing an extensible editor
							</h3>
							<p
								class="copy"
								data-aos="fade-up"
							>
								Blogr features an exceedingly intuitive interface
								which lets you focus on one thing: creating content.
								The editor supports management of multiple blogs and
								allows easy manipulation of embeds such as images,
								videos, and markdown. Extensibility with plugins and
								themes provide easy ways to add functionality or
								change the looks of a blog.
							</p>
						</div>

						<div class="info-block">
							<h3
								class="block-heading"
								data-aos="fade-right"
							>Robust content management</h3>
							<p
								class="copy"
								data-aos="fade-up"
							>
								Flexible content management enables users to easily
								move through posts. Increase the usability of yoru
								blog by adding customized categories, sections,
								format, or flow. With this functionality, you're in
								full control.
							</p>
						</div>
					</div>

					<div class="col-2">
						<img
							src="@/assets/images/illustration-editor-desktop.svg"
							class="desktop"
							alt=""
						>
						<img
							src="@/assets/images/illustration-editor-mobile.svg"
							class="mobile"
							alt=""
						>
					</div>
				</div>
			</div>
		</section>

		<section class="infrastructure">
			<div class="overlay"></div>
			<div class="outer-container">
				<div class="col-wrapper">
					<div class="col-1">
						<img
							src="@/assets/images/illustration-phones.svg"
							alt=""
						/>
					</div>
					<div class="col-2">
						<h2
							class="section-heading"
							data-aos="fade-left"
						>
							State of the Art Infrastructure
						</h2>
						<p
							class="copy"
							data-aos="fade-up"
						>
							With reliability and speed in mind, worldwide data
							centers provide the backbone for ultra-fast
							connectivity. This ensures your site will load
							instantly, no matter where your readers are, keeping
							your site competitive.
						</p>
					</div>
				</div>
			</div>
		</section>

		<section class="bottom">
			<div class="overlay"></div>
			<div class="outer-container">
				<div class="col-1">
					<img
						src="@/assets/images/illustration-laptop-desktop.svg"
						class="desktop"
						alt=""
					>
					<img
						src="@/assets/images/illustration-laptop-mobile.svg"
						class="mobile"
						alt=""
					>
				</div>

				<div class="col-2">
					<div class="info-block">
						<h3
							class="block-heading"
							data-aos="fade-left"
						>Free, open, simple</h3>
						<p
							class="copy"
							data-aos="fade-up"
						>
							Blogr is a free and open source applicatino backed
							by a large community of helpful developers. It
							supports features such as code syntax highlighting,
							RSS feeds, social media integration, thrid-party
							commenting tools, and works seamlessly with Google
							Analytics. The architecture is clean and is
							relatively easy to learn.
						</p>
					</div>

					<div class="info-block">
						<h3
							class="block-heading"
							data-aos="fade-left"
						>Powerful tooling</h3>
						<p
							class="copy"
							data-aos="fade-up"
						>
							Batteries included. We built a simple and
							straightforward CLI tool that makes customization
							and deployment a breeze, but capable of producing
							even the most complicated sites.
						</p>
					</div>
				</div>
			</div>
		</section>
	</div>
</template>

<script>
import AOS from "aos";
import "aos/dist/aos.css";

export default {
	name: "Home",
	components: {},
	created() {
		AOS.init({ duration: 800, once: true });
	},
};
</script>

<style lang="scss" scoped>
.section-heading {
	font-family: Overpass, sans-serif;
	font-size: 4.7rem;
	font-weight: 600;
	color: $headings-color;
	@include breakpoint(tablet-port) {
		font-size: 3.7rem;
	}
	@include breakpoint(mobile) {
		font-size: 3rem;
	}
}
.block-heading {
	font-family: Overpass, sans-serif;
	font-size: 3.3rem;
	font-weight: 600;
	color: $headings-color;
	@include breakpoint(tablet-land) {
		text-align: center;
	}
	@include breakpoint(tablet-port) {
		font-size: 2.7rem;
	}
	@include breakpoint(mobile) {
		font-size: 2.5rem;
	}
}
.copy {
	font-family: Overpass, sans-serif;
	line-height: 1.75;
	font-weight: 600;
	font-size: 2rem;
	@include breakpoint(tablet-land) {
		text-align: center;
		font-size: 1.8rem;
	}
	@include breakpoint(mobile) {
		font-size: 1.6rem;
	}
}

section.hero {
	position: relative;
	height: 80rem;
	padding: 0;
	background: $hero-bg-gradient;
	border-bottom-left-radius: 12rem;
	display: flex;
	align-items: center;
	justify-content: center;
	@include breakpoint(tablet-port) {
		height: 62rem;
	}
	@include breakpoint(mobile) {
		height: 55rem;
	}
	.overlay {
		position: absolute;
		width: 100%;
		height: 100%;
		z-index: 1;
		background-image: url("~@/assets/images/bg-pattern-intro.svg");
		background-size: 150%;
		background-position: -300px center;
		@include breakpoint(tablet-land) {
			background-position: center;
			background-size: 180%;
		}
		@include breakpoint(mobile) {
			background-size: 300%;
			background-position: -400px -500px;
		}
	}
	.outer-container {
		position: relative;
		z-index: 2;
	}
	.hero-heading {
		font-family: Overpass, sans-serif;
		margin: 5% 0 2rem;
		text-align: center;
		font-size: 6.5rem;
		color: #fff;
		@include breakpoint(tablet-port) {
			font-size: 4.5rem;
		}
		@include breakpoint(mobile) {
			font-size: 3.5rem;
		}
		@include breakpoint(mobile-small) {
			margin-top: 20%;
		}
	}
	.subtext {
		font-family: Overpass, sans-serif;
		text-align: center;
		font-size: 2.2rem;
		color: #fff;
		@include breakpoint(tablet-port) {
			font-size: 1.8rem;
		}
		@include breakpoint(mobile) {
			font-size: 1.6rem;
		}
	}
	.cta-container {
		margin: 4rem 0 0;
		text-align: center;
		button {
			margin: 1rem;
		}
	}
}

section.futuristicDesign,
section.bottom {
	position: relative;
	padding: 20rem 0 30rem;
	overflow-x: hidden;
	@include breakpoint(laptop) {
		padding: 14rem 0;
	}
	@include breakpoint(tablet-land) {
		padding: 10rem 0 24rem;
	}
	@include breakpoint(laptop) {
		padding: 8rem 0 24rem;
	}
	.section-heading {
		margin-bottom: 12rem;
		text-align: center;
		@include breakpoint(tablet-land) {
			margin-bottom: 4rem;
		}
	}
	.column-wrapper {
		display: flex;
		@include breakpoint(tablet-land) {
			flex-wrap: wrap;
		}
	}
	.col-1 {
		width: 50%;
		@include breakpoint(tablet-land) {
			width: 100%;
			order: 2;
		}
		.info-block {
			&:not(:last-child) {
				margin-bottom: 8rem;
			}
			.block-heading {
				margin-bottom: 2rem;
			}
			.block-heading {
				margin-bottom: 3rem;
			}
			.copy {
				color: lighten($body-copy-color, 25%);
			}
		}
	}
	.col-2 {
		position: absolute;
		width: 50%;
		height: 100%;
		right: 0;
		top: 50%;
		transform: translateY(-50%);
		@include breakpoint(tablet-land) {
			width: 100%;
			position: static;
			height: unset;
			top: unset;
			transform: none;
			order: 1;
			text-align: center;
			margin-bottom: 4rem;
		}
		img {
			max-width: unset;
			height: 85%;
			position: relative;
			top: 50%;
			right: -15%;
			transform: translateY(-50%);
			@include breakpoint(tablet-land) {
				right: unset;
				height: unset;
				width: 80%;
				margin: 0 auto;
				transform: none;
				position: static;
			}
			&.desktop {
				@include breakpoint(tablet-land) {
					display: none;
				}
			}
			&.mobile {
				display: none;
				@include breakpoint(tablet-land) {
					display: block;
				}
				@include breakpoint(mobile) {
					width: 100%;
				}
			}
		}
	}
}

section.infrastructure {
	position: relative;
	height: 50rem;
	background: $body-bg-gradient;
	border-bottom-left-radius: 12rem;
	border-top-right-radius: 12rem;
	@include breakpoint(tablet-land) {
		height: auto;
	}
	.overlay {
		position: absolute;
		top: 0;
		width: 55%;
		height: 100%;
		background-image: url("~@/assets/images/bg-pattern-circles.svg");
		background-size: 100%;
		background-repeat: no-repeat;
		background-position: bottom;
		@include breakpoint(ipadPro) {
			background-size: 150%;
		}
		@include breakpoint(tablet-land) {
			width: 100%;
			background-position: center -350px;
			background-size: 105%;
		}
	}
	.outer-container {
		position: relative;
		z-index: 2;
		height: 100%;
	}
	.section-heading {
		margin-bottom: 2rem;
		text-align: left;
		color: #fff;
		@include breakpoint(tablet-land) {
			text-align: center;
		}
	}
	.copy {
		color: darken(#fff, 30%);
	}
	.col-wrapper {
		display: flex;
		height: 100%;
		@include breakpoint(tablet-land) {
			flex-wrap: wrap;
		}
	}
	.col-1 {
		width: 50%;
		@include breakpoint(tablet-land) {
			width: 100%;
		}
		img {
			position: absolute;
			top: -18%;
			left: -5%;
			width: 50%;
			@include breakpoint(ipadPro) {
				left: -2%;
				top: 0;
			}
			@include breakpoint(tablet-land) {
				position: relative;
				left: 50%;
				top: -175px;
				width: 40rem;
				transform: translateX(-50%);
			}
		}
	}
	.col-2 {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 50%;
		height: 100%;
		@include breakpoint(tablet-land) {
			width: 100%;
			padding-bottom: 8rem;
			margin-top: -16rem;
			text-align: center;
		}
	}
}

section.bottom {
	padding: 20rem 0;
	margin-top: 10rem;
	@include breakpoint(laptop) {
		margin-top: 4rem;
	}
	@include breakpoint(tablet-land) {
		margin-top: 0;
		padding: 8rem 0;
	}
	@include breakpoint(tablet-port) {
		padding: 6rem 0 4rem;
	}

	.col-1 {
		position: absolute;
		width: 50%;
		height: 100%;
		left: 0;
		top: 50%;
		transform: translateY(-50%);
		@include breakpoint(tablet-land) {
			width: 100%;
			position: static;
			height: unset;
			top: unset;
			transform: none;
			order: 1;
			text-align: center;
			margin-bottom: 4rem;
		}
		img {
			max-width: unset;
			height: 90%;
			position: absolute;
			top: 50%;
			right: 10%;
			transform: translateY(-50%);
			@include breakpoint(tablet-land) {
				right: unset;
				height: unset;
				width: 80%;
				margin: 0 auto;
				transform: none;
				position: static;
			}
			&.desktop {
				@include breakpoint(tablet-land) {
					display: none;
				}
			}
			&.mobile {
				display: none;
				@include breakpoint(tablet-land) {
					display: block;
				}
				@include breakpoint(mobile) {
					width: 100%;
				}
			}
		}
	}
	.col-2 {
		position: static;
		margin-left: auto;
		width: 50%;
		top: unset;
		transform: none;
		@include breakpoint(tablet-land) {
			width: 100%;
			order: 2;
		}
		.info-block {
			&:not(:last-child) {
				margin-bottom: 8rem;
			}
			.block-heading {
				margin-bottom: 2rem;
			}
			.block-heading {
				margin-bottom: 3rem;
			}
			.copy {
				color: lighten($body-copy-color, 25%);
			}
		}
	}
}
</style>
