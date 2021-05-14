<template>
    <footer class="footer">
        <div class="outer-container">
            <div class="logo-container">
                <img src="@/assets/images/logo.svg" alt="Blogr logo">
            </div>
            
            <div class="footer-nav">
                <ul>
                    <li>Product</li>
                    <li>Overview</li>
                    <li>Pricing</li>
                    <li>Marketplace</li>
                    <li>Features</li>
                    <li>Integrations</li>
                </ul>

                <ul>
                    <li>Company</li>
                    <li>About</li>
                    <li>Team</li>
                    <li>Blog</li>
                    <li>Careers</li>
                </ul>

                <ul>
                    <li>Connect</li>
                    <li>Contact</li>
                    <li>Newsletter</li>
                    <li>LinkedIn</li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<script>
    export default {
        name: "TheFooter",
    }
</script>

<style lang="scss" scoped>
.footer {
    margin-top: 10rem;
    height: 45rem;
    padding: 10rem 0;
    background-color: $footer-bg-color;
    border-top-right-radius: 12rem;
    @include breakpoint(laptop) {
		margin-top: 0;
    }
    .outer-container {
        display: flex;
        @include breakpoint(tablet-land) {
            flex-wrap: wrap;
        }
    }

    .logo-container {
        width: 30%;
        @include breakpoint(tablet-land) {
            width: 100%;
        }
        img {
            width: 12rem;
        }
    }

    .footer-nav {
        display: flex;
        justify-content: space-between;
        width: 55%;
        color: $footer-text-color;
        
        li {
            font-size: 2rem;
            
        }
        li:first-of-type {
            font-weight: 600;
            margin-bottom: 3rem;
        }
        li:not(:first-of-type) {
            color: darken($footer-text-color, 15%);
            padding: .75rem 0;
            cursor: pointer;
            &:hover {
                text-decoration: underline;
                
            }
        }
    }
}

</style>