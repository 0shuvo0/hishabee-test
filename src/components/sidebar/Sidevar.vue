<template>
    <div class="sidebar">
        <SidebarMenuSection />
        <SidebarPriceSelect />
    </div>
</template>

<script>
import SidebarMenuSection from "@/components/sidebar/SidebarMenuSection.vue"
import SidebarPriceSelect from "@/components/sidebar/SidebarPriceSelect.vue"

export default {
    components: {
        SidebarMenuSection,
        SidebarPriceSelect
    }
}
</script>