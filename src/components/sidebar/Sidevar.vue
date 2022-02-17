<template>
    <div class="sidebar" :class="{active: isOpen}">
        <SidebarMenuSection />
        <SidebarPriceSelect />
        <button class="sidebar-btn" @click="isOpen = !isOpen">
            <i class="bi-x" v-if="isOpen"></i>
            <i class="bi-list" v-else></i>
        </button>
    </div>
</template>

<script>
import SidebarMenuSection from "@/components/sidebar/SidebarMenuSection.vue"
import SidebarPriceSelect from "@/components/sidebar/SidebarPriceSelect.vue"

export default {
    components: {
        SidebarMenuSection,
        SidebarPriceSelect
    },
    data: () => ({
        isOpen: false
    })
}
</script>

<style>
.sidebar-btn{
    position: fixed;
    bottom: 1em;
    right: 1em;
    background-color: var(--primary-color);
    height: 60px;
    width: 60px;
    border-radius: 50%;
    color: #fff;
    font-size: 2em;
    box-shadow: 0 3px 7px rgba(0, 0, 0, 0.1);
    opacity: 0.35;
    transition: opacity .2s;
    display: none;
}
.sidebar-btn:hover{
    opacity: 1;
}
</style>