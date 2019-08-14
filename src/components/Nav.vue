<template>
    <div id="nav">
        <router-link to="/" class="left">TW</router-link>
        <router-link to="/photography">Photography</router-link>
        <router-link to="/about">About</router-link>
    </div>
</template>

<script>
export default {
    name: 'Nav',
};
</script>

<style lang="scss" scoped>
#nav {
    padding: 2rem 4rem 2rem 2rem;
    width: 100%;
    display: flex;
    justify-content: flex-end;

    a {
        color: $black;
        text-decoration: none;
        font-family: 'IBM Plex Sans', sans-serif;
        margin-right: 2rem;
    }
}
.left {
    position: absolute;
    left: 5%;
}
</style>
