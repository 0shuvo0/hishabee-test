<template>
    <div class="sidebar-section">
        <div class="section--title flex-center" @click="isCollapsed = !isCollapsed">
            <span>
                Price
            </span>
            <i class="bi-chevron-down" :class="{ open: !isCollapsed }"></i>
        </div>
        <div class="section--content" :class="{ active: !isCollapsed }">
            <RangeSlider />
        </div>
    </div>
</template>

<script>
import RangeSlider from "@/components/RangeSlider.vue"

export default {
    components: {
        RangeSlider
    },
    data: () => ({
        isCollapsed: false
    })
}
</script>