<template>
    <div id="photography" class="container">
        <ul>
            <li v-for="(image, index) in images" :key="index">{{ imageIndex }}</li>
        </ul>
        <button @click="nextImage">next</button>
    </div>
</template>

<script>
export default {
    name: 'photography',
    data: () => {
        return {
            imageIndex: 0,
            images: ['test', 'test'],
        };
    },
    methods: {
        nextImage: function() {
            this.imageIndex += 1;
        },
    },
};
</script>

<style>
</style>