<template>
    <div id="app">
        <Nav />
        <transition
            name="router-animation"
            enter-class="router-before-enter"
            enter-active-class="router-enter"
            leave-active-class="router-leave"
        >
            <router-view />
        </transition>
        <!-- <Ball /> -->
    </div>
</template>

<script>
import Vue from 'vue';
import Nav from './components/Nav';
import Ball from './components/Ball';

// AOS
import AOS from 'aos';
import 'aos/dist/aos.css'; // You can also use <link> for styles
AOS.init();

// Sticky
import Sticky from 'vue-sticky-directive';
Vue.use(Sticky);

export default {
    name: 'App',
    components: {
        Nav,
        Ball,
    },
};
</script>
<style lang="scss">
@include css-reset;
html {
    font-size: 62.5%; // 1rem = 10px
    font-family: 'IBM Plex Serif', serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

body {
    font-size: 1.8rem; // Font size = 18px
    background: $background-color;
    color: $black;
}

.container {
    width: 100%;
    padding: 10% 10% 5%;
}

.router-enter,
.router-before-enter,
.router-leave {
    transition: 800ms ease-in-out;
}

.router-enter {
    position: fixed;
    left: 0;
    transform: translateY(0);
}
.router-leave {
    position: fixed;
    left: 0;
    transform: translateY(-100%);
}
.router-before-enter {
    transform: translateY(100vh);
}

h1,
h2,
h3,
h4,
h5,
h6 {
    font-family: 'IBM Plex Sans', sans-serif;
    font-weight: 700;
    text-transform: uppercase;
}
h1 {
    $h1: (
        576: 32,
        1024: 36,
    );
    font-size: least-squares-fit($h1);
}
.page {
    width: 100%;
    header {
        text-align: center;

        h1 {
            margin-bottom: 9rem;
            max-width: 30ch;
            margin: 0 auto 5rem;
        }
        p {
            margin: 0 auto;
        }
    }
    section {
        background: coral;
        margin: 2rem 2rem 0;
        padding: 2rem;
        height: calc(100vh - 4rem);
        position: relative;
        display: grid;
        grid-template-columns: 15% 1fr;
        align-items: center;

        .box {
            position: relative;
            top: 20vh;
            width: 180%;
            display: inline-block;
            padding: 2rem;
            background-color: $background-color;
            z-index: 1;
        }
        img {
            max-width: 100%;
            max-height: 100%;
        }
    }
}
h4 {
    letter-spacing: 0.06em;
    margin-bottom: 1rem;
    margin: 0;
}

p {
    max-width: 70ch;

    &.large {
        font-size: 2.4rem;
    }
}
</style>
