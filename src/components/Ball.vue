<template>
    <div class="ball"></div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
$ball-size: 12px;
.ball {
    position: absolute;
    left: 5%;
    top: 10%;
    width: $ball-size;
    height: $ball-size;
    border-radius: $ball-size;
    background: coral;
}
</style>