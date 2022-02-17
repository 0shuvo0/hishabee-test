<template>
    <div>
        <section class="range-slider">
            <input v-model="minVal" :min="min" :max="max" :step="step" type="range" name="minrange">
            <input v-model="maxVal" :min="min" :max="max" :step="step" type="range" name="maxrange">
        </section>
        <div class="range-vals">
            <span>${{ minVal }}</span>
            <span>${{ maxVal }}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        min: {
            type: Number,
            default: 0
        },
        max: {
            type: Number,
            default: 1000
        },
        step: {
            type: Number,
            default: 1
        }
    },
    data: () => ({
        minVal: 100,
        maxVal: 900
    })
}
</script>

<style scoped>
  section.range-slider {
    position: relative;
    height: 25px;
    text-align: center;
}

section.range-slider input {
    pointer-events: none;
    position: absolute;
    overflow: hidden;
    width: 100%;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
}

section.range-slider input::-webkit-slider-thumb {
    pointer-events: all;
    position: relative;
    z-index: 1;
}

section.range-slider input::-moz-range-thumb {
    pointer-events: all;
    position: relative;
    z-index: 10;
    -moz-appearance: none;
}
section.range-slider input::-moz-range-track {
    position: relative;
    z-index: -1;
}
.range-vals{
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
    font-size: .9em;
}

</style>