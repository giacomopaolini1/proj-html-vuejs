<script>
    import {store} from '../data/store'

    export default {
        name: "AppNavbar",
        data() {
            return {
                store,
            }
        }
    }
</script>

<template>
    <section class="container">
        <div class="row">
            <div class="p-4 d-flex justify-content-between align-items-center">
                <div>
                    <a href="#"><img src="../assets/images-construction/imagesPush/construction_logo.png" alt="logo"></a>
                </div>
                <div>
                    <ul class="d-flex align-items-center gap-4 list-style-none list-inline">
                        <li v-for="item in this.store.navBar">
                            <a :href="item.link" class="link-unstyled outline-text">{{ item.label }}</a>
                        </li>
                        <button><a>GET QUOTE</a></button>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/variables.scss' as *;
@use '../styles/mixins.scss' as *;

    li a {
        color: $black;
        text-decoration: none;
        font-weight: 400;
    }
    li a:hover {
        -webkit-text-stroke: 1px $black;
    }

    button {
        @include button(10rem, 0.5rem, $primary, $black);
        border: 2px solid $black;
    }
    button:hover {
        background-color: $black;
        color: $white;
    }

</style>
