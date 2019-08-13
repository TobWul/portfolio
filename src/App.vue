<template>
    <div id="app">
        <Nav />
        <router-view />
    </div>
</template>

<script>
import Nav from './components/Nav'
import AOS from 'aos'
import 'aos/dist/aos.css' // You can also use <link> for styles
// ..
AOS.init()

export default {
    name: 'App',
    components: {
        Nav,
    },
}
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
    background: #e5e5e5;
    color: $black;
}

.container {
    padding: 10% 10% 5%;
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
    max-width: 30ch;
    margin: 0 auto;
}
h1 {
    $h1: (
        576: 32,
        1024: 36,
    );
    font-size: least-squares-fit($h1);
}
header {
    text-align: center;

    h1 {
        margin-bottom: 9rem;
    }
    p {
        margin: 0 auto;
    }
}
h4 {
    letter-spacing: 0.06em;
    margin-bottom: 1rem;
}

p {
    max-width: 70ch;

    &.large {
        font-size: 2.4rem;
    }
}
</style>
