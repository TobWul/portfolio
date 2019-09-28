<template>
    <div id="nav">
        <router-link to="/" class="left">
            <h4>
                Tobias
                <br />Wulvik
            </h4>
        </router-link>
        <router-link to="/about">
            <h6>About</h6>
        </router-link>
    </div>
</template>

<script>
export default {
    name: 'Nav',
};
</script>

<style lang="scss" scoped>
#nav {
    padding: 3rem 5%;
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
