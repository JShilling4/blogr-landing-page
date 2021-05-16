<template>
    <button
        :class="[
            'button',
            { hovering: isHovering && showHoverEffect, transparent: !filled },
        ]"
        :style="styleObject"
        @mouseover="isHovering = true"
        @mouseleave="isHovering = false"
    >
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: "AppButton",
    props: {
        showShadow: {
            type: Boolean,
            default: true,
        },
        showHoverEffect: {
            type: Boolean,
            default: true,
        },
        minWidth: {
            type: String,
            default: "15rem",
        },
        fontSize: {
            type: String,
            default: "1.6rem",
        },
        filled: {
            type: Boolean,
            default: true,
        },
    },
    data() {
        return {
            styleObject: {
                boxShadow: this.showShadow
                    ? "0 13px 15px -13px rgb(242, 95, 58)"
                    : "",
                minWidth: this.minWidth,
                fontSize: this.fontSize,
            },
            isHovering: false,
        };
    },
};
</script>

<style lang="scss" scoped>
.button {
    font-family: Ubuntu, sans-serif;
    padding: 1.4rem 0 1.6rem;
    border: none;
    border-radius: 3rem;
    outline: none;
    font-weight: 600;
    // letter-spacing: 0.6px;
    color: $cta-text-color;
    background-color: #fff;
    text-align: center;
    border: 1px solid #fff;
    cursor: pointer;
    transition: background-color 0.3s, letter-spacing 0.3s;
    &.transparent {
        color: #fff;
        background-color: transparent;
    }
    &.hovering {
        color: #fff;
        background-color: $cta-hover-bg-color;
        letter-spacing: 0.6px;
    }
    &.transparent.hovering {
        color: $cta-hover-bg-color;
        background-color: #fff;
    }
}
</style>