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
            <div class="outer-container">
                <div class="col-1"></div>
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

section.futuristicDesign {
    position: relative;
    padding: 20rem 0;
    overflow-x: hidden;
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
    .col-2 {
    }
}

section.infrastructure {
    background: $body-bg-gradient;
    .section-heading {
        color: #fff;
    }
}
</style>
