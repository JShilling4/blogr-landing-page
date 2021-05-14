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
			<div class="overlay"></div>
			<div class="outer-container">
				<h2 class="section-heading">Designed for the future</h2>

				<div class="col-1">
					<div class="info-block">
						<h3 class="block-heading">
							Introducing an extensible editor
						</h3>
						<p class="copy">
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
						<h3 class="block-heading">Robust content management</h3>
						<p class="copy">
							Flexible content management enables users to easily
							move through posts. Increase the usability of yoru
							blog by adding customized categories, sections,
							format, or flow. With this functionality, you're in
							full control.
						</p>
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
						<h2 class="section-heading">
							State of the Art Infrastructure
						</h2>
						<p class="copy">
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
					<div class="info-block">
						<h3 class="block-heading">Free, open, simple</h3>
						<p class="copy">
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
						<h3 class="block-heading">Powerful tooling</h3>
						<p class="copy">
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
export default {
	name: "Home",
	components: {},
};
</script>

<style lang="scss" scoped>
.section-heading {
	font-family: Overpass, sans-serif;
	font-size: 4.7rem;
	font-weight: 600;
	color: $headings-color;
}
.block-heading {
	font-family: Overpass, sans-serif;
	font-size: 3.3rem;
	font-weight: 600;
	color: $headings-color;
}
.copy {
	font-family: Overpass, sans-serif;
	line-height: 1.75;
	font-weight: 600;
	font-size: 2rem;
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
	.overlay {
		position: absolute;
		width: 100%;
		height: 100%;
		z-index: 1;
		background-image: url("~@/assets/images/bg-pattern-intro.svg");
		background-size: 150%;
		background-position: -300px center;
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
	}
	.subtext {
		font-family: Overpass, sans-serif;
		text-align: center;
		font-size: 2.2rem;
		color: #fff;
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
	padding: 20rem 0;
	overflow-x: hidden;
	@include breakpoint(laptop) {
		padding: 14rem 0;
	}
	.overlay {
		position: absolute;
		height: 90%;
		width: 50%;
		right: -12%;
		top: 50%;
		transform: translateY(-50%);
		background-image: url("~@/assets/images/illustration-editor-desktop.svg");
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
		@include breakpoint(desktop) {
			width: 80%;
			right: -45%;
		}
		@include breakpoint(ipadPro) {
			width: 100%;
			right: -60%;
		}
		@include breakpoint(laptop) {
			height: 80%;
		}
	}
	.section-heading {
		margin-bottom: 14rem;
		text-align: center;
	}
	.col-1 {
		width: 50%;
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
				font-family: Overpass, sans-serif;
				color: lighten($body-copy-color, 25%);
				line-height: 1.75;
				font-weight: 600;
				font-size: 2rem;
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
	}
	.copy {
		color: darken(#fff, 30%);
	}
	.col-wrapper {
		display: flex;
		height: 100%;
	}
	.col-1 {
		width: 50%;
		img {
			position: absolute;
			top: -18%;
			left: -5%;
			width: 50%;
			@include breakpoint(ipadPro) {
				left: -2%;
				top: 0;
			}
		}
	}
	.col-2 {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 50%;
		height: 100%;
	}
}

section.bottom {
	padding: 20rem 0;
	margin-top: 10rem;
    @include breakpoint(laptop) {
		margin-top: 4rem;
    }
	.overlay {
		left: -10%;
		background-image: url("~@/assets/images/illustration-laptop-desktop.svg");
		@include breakpoint(desktop) {
			left: -45%;
		}
		@include breakpoint(ipadPro) {
			left: -55%;
		}
	}
	.col-1 {
		margin-left: auto;
	}
}
</style>
