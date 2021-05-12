<template>
    <div class="home">
        <div class="hero">
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
        </div>
    </div>
</template>

<script>
export default {
    name: "Home",
    components: {},
};
</script>

<style lang="scss" scoped>
.hero {
    position: relative;
    height: 60rem;
    padding: 0;
    background: $hero-bg-gradient;
    border-bottom-left-radius: 11rem;
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
        background-position: -200px center;
    }
    .outer-container {
        position: relative;
        z-index: 2;
    }
    .hero-heading {
        font-family: Overpass, sans-serif;
        margin: 10% 0 2rem;
        font-size: 6rem;
        color: #fff;
    }
    .subtext {
        font-family: Overpass, sans-serif;
        text-align: center;
        font-size: 1.8rem;
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
</style>
