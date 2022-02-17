<template>
    <div>
        <p class="title">Fruits Collection</p>
        <ProductsNav />
        <div class="products-container">
            <ProductCard
             v-for="i in 9"
             :key="i"
             :id="i"
            />
        </div>
        <p class="text-center mt-2">
            <button class="btn" style="width: 220px">Load Mode</button>
        </p>
    </div>
</template>

<script>
import ProductsNav from "@/components/products/ProductsNav.vue"
import ProductCard from "@/components/products/ProductCard.vue"

export default {
    components: {
        ProductsNav,
        ProductCard
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

.products-container{
    margin-top: 2em;
    display: grid;
    gap: 1.5em;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
}
</style>