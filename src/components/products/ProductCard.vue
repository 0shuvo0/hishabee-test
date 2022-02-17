<template>
    <div class="product-card">
        <div class="product-img">
            <CustomRatioImg
            pt="110%"
            :src="`/img/${id}.png`"
            />
            <div class="controls">
                <div class="badge">New</div>
                <div style="margin: 0 auto -6em auto">
                    <div class="qty-control">
                        <button class="qty-btn" @click="qty > 1 && qty--"><i class="bi-dash" style="line-height: 1.7"></i></button>
                        <button class="qty-btn num">{{qty}}</button>
                        <button class="qty-btn" @click="qty++">+</button>
                    </div>
                    <button class="btn">Add To Cart</button>
                </div>
                <button class="details-btn">
                    Details
                    <i class="bi-arrow-right"></i>
                </button>
            </div>
        </div>
        <div class="product-info">
            <p class="category-name">Category Name</p>
            <p class="rating">
                <i class="bi-star-fill"></i>
                <i class="bi-star-fill"></i>
                <i class="bi-star-fill"></i>
                <i class="bi-star-fill"></i>
                <i class="bi-star-fill"></i>
                <span>(121)</span>
            </p>
            <p class="product-name">Product Name</p>
            <p class="product-price flex-center">
                <span class="price">$200.00</span>
                <span class="price-old">$300.00</span>
            </p>
        </div>
    </div>
</template>

<script>
import CustomRatioImg from "@/components/CustomRatioImg.vue"

export default {
    props: ['id'],
    components: {
        CustomRatioImg
    },
    data: () => ({
        qty: 1
    })
}
</script>

<style>
.product-img{
    position: relative;
    overflow: hidden;
    border-radius: 5px;
}
.product-img .controls{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .3);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    transform: translateY(100%);
    opacity: 0;
    transition: transform .5s, opacity 1s;
}
.product-img:hover .controls{
    transform: translateY(0);
    opacity: 1;
}
.product-img .controls .badge{
    background-color: #333333;
    display: inline-block;
    width: auto;
    margin: 2em auto 0 2em;
    color: #fff;
    padding: .3em .75em .5em 2.5em;
    border-radius: 5px;
    font-size: .95em;
}
.product-img .controls .btn{
    width: 230px;
    margin-top: 1em;
}
.product-img .controls .details-btn{
    padding-block: 1em;
    background-color: #F2F2F2;
    border-radius: 5px;
    color: #999;
    font-size: 1em;
}
.details-btn i{
    margin-left: .5em;
}
.qty-control .qty-btn{
    height: 60px;
    width: 60px;
    border: 1px solid #fff;
    background-color: transparent;
    border-radius: 50%;
    color: #fff;
    font-size: 2em;
}
.qty-control .qty-btn:hover{
    background-color: rgba(255, 255, 255, .3);
}
.qty-control .qty-btn.num{
    background-color: #fff;
    color: var(--primary-color);
    margin-inline: .75em;
    cursor: initial;
}

.product-info{
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: .5em;
}
.product-info .category-name{
    font-size: .8em;
    color: #BDBDBD;
    margin-top: 1.25em;
}
.product-info .rating{
    color: #FABE50;
}
.rating i{
    margin-right: .25em;
}
.rating span{
    color: #4F4F4F;
    margin-left: .25em;
}
.product-info > p{
    margin-top: .5em;
}
.product-info .product-name{
    font-size: 1.25em;
    font-weight: 500;
    color: #333333;
}
.product-info .product-price .price{
    color: #FF5C00;
    font-weight: 500;
    font-size: 1.2em;
}
.product-info .product-price .price-old{
    color: #BDBDBD;
    text-decoration: line-through;
    font-size: 1em;
    margin-left: 1em;
}
</style>