<template>
    <div class="sidebar-section">
        <div class="section--title flex-center" @click="isCollapsed = !isCollapsed">
            <span>
                Categories
            </span>
            <i class="bi-chevron-down" :class="{ open: !isCollapsed }"></i>
        </div>
        <div class="section--content" :class="{ active: !isCollapsed }">
            <SidebarMenuItem
             v-for="(item, index) in menu"
             :key="index"
             :item="item"
             :isSubItem="false"
             />
        </div>
    </div>
</template>

<script>
import menu from "@/data/menu.json"
import SidebarMenuItem from "@/components/SidebarMenuItem.vue"
export default {
    components: {
        SidebarMenuItem
    },
    data: () => ({
        isCollapsed: true,
        menu
    })
}
</script>

<style>
.sidebar-section{
    border: 1px solid var(--primary-light);
    border-radius: 10px;
    overflow: hidden;
}

.section--title{
    padding: 1em;
    background: var(--primary-light);
    border-bottom: 1px solid var(--primary-light);
    font-size: 1.1em;
    font-weight: 600;
    cursor: pointer;
}
.section--title i{
    transform: rotate(0deg);
    margin-left: .5em;
    transition: transform .35s;
}
.section--title i.open{
    transform: rotate(180deg);
}

.section--content{
    height: 0;
    overflow: hidden;
    padding: 0 1.25em;
    margin: 1.25m 0;
}
.section--content.active{
    height: auto;
    margin: 1.25em 0;
}
</style>