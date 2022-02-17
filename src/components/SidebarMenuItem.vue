<template>
    <div class="menu-item" :class="{submenu: isSubItem}" v-if="typeof item == 'object'">
        <div class="section--title flex-center" @click="isCollapsed = !isCollapsed">
            <span>
                <span class="icon" v-if="item.icon">
                    {{ item.icon }}
                </span>
                {{ item.title }}
            </span>
            <i class="bi-chevron-down" :class="{ open: !isCollapsed }"></i>
        </div>
        <div class="section--content" :class="{ active: !isCollapsed, sub: item.childerns }">
            <SidebarMenuItem
            v-for="(subItem, index) in item.childerns"
            :key="index"
            :item="subItem"
            :isSubItem="true"
            />
        </div>
    </div>
    <p v-else class="menu-item-text" :class="{submenu: isSubItem}">{{ item }}</p>
</template>

<script>
export default {
    name: 'SidebarMenuItem',
    props: ['item', 'isSubItem'],
    data: () => ({
        isCollapsed: true
    })
}
</script>

<style>
.menu-item .section--title{
    background: none;
    border-bottom: 1px solid var(--primary-light);
    padding-inline: 0;
    padding-block: .75em;
    font-weight: 400;
    font-size: .85em;
}
.menu-item.submenu{
    border-left: 2px solid #E0E0E0;
}
.menu-item.submenu .section--title{
    border-bottom: none;
    padding-left: 1.25em;
}
.menu-item-text.submenu{
    border-left: 2px solid #E0E0E0;
    padding-left: 1.25em;
}
.section--title .icon{
    margin-right: .5em;
}
.section--content.sub{
    padding: 0 0 0 .5em;
}
.menu-item-text{
    color: var(--primary-color); 
    padding: .25em 0;
    font-weight: 500;
    font-size: .85em;
    margin-left: 1em;
}
.menu-item-text:hover{
    text-decoration: underline;
    cursor: pointer;
}
</style>