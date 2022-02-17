<template>
    <div class="custom-ratio-img" :style="{paddingTop: pt}">
        <img :src="src" alt="" />
    </div>
</template>

<script>
export default {
    props: ['src', 'pt'],
}
</script>

<style>
.custom-ratio-img {
    position: relative;
    width: 100%;
    height: 0;
}
.custom-ratio-img img {
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}
</style>