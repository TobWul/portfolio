<template>
    <div id="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/sentif">Sentif</router-link>
    </div>
</template>

<script>
export default {
    name: 'Nav',
}
</script>

<style lang="scss" scoped>
#nav {
    width: 100%;
}
</style>
