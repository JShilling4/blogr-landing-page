<template>
    <header class="header">
        <img src="@/assets/images/logo.svg" alt="Manage logo" class="logo" />

        <nav v-if="showMobileMenu" class="nav">
            <div class="nav-left">
                <a href="#" class="nav-item">
                    Product<img
                        src="@/assets/images/icon-arrow-light.svg"
                        class="arrow"
                    />
                </a>
                <a href="#" class="nav-item"
                    >Company<img
                        src="@/assets/images/icon-arrow-light.svg"
                        class="arrow"
                /></a>
                <a href="#" class="nav-item"
                    >Connect<img
                        src="@/assets/images/icon-arrow-light.svg"
                        class="arrow"
                /></a>
            </div>
            <div class="nav-right">
                <a href="#" class="nav-item">Login</a>
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
            margin: 0 1.85rem;
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
                text-decoration: underline;
            }
            .arrow {
                margin-left: 0.5rem;
            }
        }
    }
    button {
        margin-left: auto;
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