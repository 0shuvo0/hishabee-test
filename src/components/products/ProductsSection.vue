<template>
    <div>
        <p class="title">Fruits Collection</p>
        <ProductsNav />
    </div>
</template>

<script>
import ProductsNav from "@/components/products/ProductsNav.vue"

export default {
    components: {
        ProductsNav
    }
}
</script>

<style>
.title{
    font-size: 2em;
    font-weight: bold;
    color: #333333;
    margin-bottom: .5em;
}
</style>