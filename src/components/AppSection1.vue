<script>
    import {store} from '../data/store'

    export default {
        name: "AppSection1",
        data() {
            return {
                store,
            }
        }
    }
</script>

<template>
    <section>
        <div class="container-fluid my-bg-primary">
            <div class="container text-center">
                <div class="row p-4">
                    <div class="mb-3">
                        <p>Do You Have A Construction Project We Can Help With?</p>
                    </div>
                </div>
            </div>
        </div>
        <button class="centered-button">GET A FREE QUOTE</button>
        <div class="container">
            <div class="row">
                <div class="text-center my-margin-top mb-5">
                    <h3>Specialists In Modern Construction</h3>
                    <div class="my-line my-4"></div>
                    <p class="my-description">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Saepe error asperiores dignissimos! Explicabo alias illo delectus beatae, necessitatibus reiciendis. Sequi ipsum reiciendis quod? Tempora et nisi iste. Fuga, nisi totam!</p>
                </div>
            </div>
        </div>
        <div class="container-fluid my-max-width">
            <div class="row">
                <div class="d-flex justify-content-evenly mt-5 mb-5">
                    <div v-for="card in this.store.cardSection1" class="my-card text-center flip-card">
                        <div class="flip-card-inner">
                            <div class="flip-card-front d-flex flex-column align-items-center justify-content-center">
                                <div class="circle-icon mb-3">
                                    <span v-html="card.icon"></span>
                                </div>
                                <h4 class="mb-3">{{ card.title }}</h4>
                                <p>{{ card.description }}</p>
                            </div>
                            <div class="flip-card-back">
                                <h4 class="mt-4">ARTFULLY CRAFTED</h4>
                                <p class="my-3">Lorem ipsum dolor sit, amet consectetur adipisicing elit.</p>
                                <button>GET A QUOTE</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/variables.scss' as *;
@use '../styles/mixins.scss' as *;

    section {
        position: relative;
    }

    .centered-button {
        position: absolute;
        top: 15.5%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .my-bg-primary {
        background-color: lightgray;
        p {
            font-size: 2rem;
            font-weight: 400;
        }
    }

    button {
        @include button(15rem, 0.5rem, $black, $white);
        border: 2px solid $white;
    }
    button:hover {
        background-color: $white;
        color: $black;
        border: 2px solid $black;
    }

    .my-margin-top {
        margin-top: 7rem;
    }

    .my-line {
        max-width: 12rem;
        height: 0.15rem;
        margin: 0 auto;
        background-color: lightgray;
    }

    .my-description {
        margin-left: 15rem;
        margin-right: 15rem;
        color: $description;
    }

    .my-max-width {
        max-width: 1920px;
    }

    .my-card {
        width: 20rem;
    }

    .circle-icon {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 50px;
        height: 50px;
        border-radius: 50%;
        border: 2px solid rgb(145, 145, 145);
        span {
            color: rgb(145, 145, 145);
        }
    }

    /*************CARD*************/
    .flip-card {
    background-color: transparent;
    width: 300px;
    height: 200px;
    perspective: 1000px;
    }

    .flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.8s;
    transform-style: preserve-3d;
    }

    .flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
    }

    .flip-card-front, .flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden; /* Safari */
    backface-visibility: hidden;
    }

    .flip-card-front {
    background-color: #ffffff;
    color: black;
    }

    .flip-card-back {
    background-color: ffffff;
    color: black;
    transform: rotateY(180deg);
    border: 1px solid $deepGray;
        button {
            @include button(10rem, 0.5rem, $black, $primary);
        }
        button:hover {
            @include button(10rem, 0.5rem, $primary, $black);
            border: 0.5px solid $black;
        }
    }
</style>