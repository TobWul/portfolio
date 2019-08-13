<template>
    <div id="app">
        <Nav />
        <router-view />
    </div>
</template>

<script>
import Nav from './components/Nav'

export default {
    name: 'App',
    components: {
        Nav,
    },
}
</script>

<style lang="scss">
html {
    font-size: 62.5%; // 1rem = 10px
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
body {
    font-size: 1.8rem; // Font size = 18px
}
</style>
