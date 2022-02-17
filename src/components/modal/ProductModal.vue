<template>
    <div class="modal-wrapper">
        <div class="modal">
            <i class="bi-x modal-close" @click="$emit('close')"></i>
            <div class="modal-content">
                <div class="img">
                    <CustomRatioImg src="/img/product/1.png" pt="100%" />
                    <div class="preview-imgs flex-center">
                        <CustomRatioImg src="/img/product/2.png" pt="17%" />
                        <CustomRatioImg src="/img/product/3.png" pt="17%" />
                        <CustomRatioImg src="/img/product/4.png" pt="17%" />
                        <CustomRatioImg src="/img/product/5.png" pt="17%" />
                        <CustomRatioImg src="/img/product/6.png" pt="17%" />
                    </div>
                    <p class="text-center">
                        <i class="bi-eye"></i>
                        <span>View more details</span>
                    </p>
                </div>
                <div class="info">
                    <div class="status">
                        <span class="status-text">Status</span>
                        <span class="status-value">In Stock</span>
                    </div>
                    <p class="product-name">
                        Product full name here
                    </p>
                    <p class="rating">
                        <i class="bi-star-fill"></i>
                        <i class="bi-star-fill"></i>
                        <i class="bi-star-fill"></i>
                        <i class="bi-star-fill"></i>
                        <i class="bi-star-fill"></i>
                        <span>10 reviews</span>
                    </p>
                    <p class="price">
                        <span class="current">$59.00</span>
                        <span class="previous">$69.00</span>
                        <span class="vat">(+15% Vat Included)</span>
                    </p>
                    <p class="sell-count">20 Products sold in last 12 hours</p>
                    <div class="qty-ctrl">
                        <span class="qty-label">quantity</span>
                        <div class="qty-ctrl-wrapper">
                            <button class="qty-btn" @click="qty > 1 && qty--">
                                <i class="bi-dash"></i>
                            </button>
                            <button class="qty-btn num">
                                {{qty}}
                            </button>
                            <button class="qty-btn" @click="qty++">
                                +
                            </button>
                        </div>
                        <span class="qty-stock">Only 10 Item Left!</span>
                    </div>
                    <button class="btn block">Add to cart</button>
                    <button class="btn block buy-now">Buy Now</button>
                    <div class="nav flex-center">
                        <div class="nav-item">
                            <i class="bi-heart"></i>
                            <span>Add to wishlist</span>
                        </div>
                        <div class="nav-item">
                            <i class="bi-arrow-left-right"></i>
                            <span>Add to compare</span>
                        </div>
                        <div class="nav-item">
                            <i class="bi-share"></i>
                            <span>Add to wishlist</span>
                        </div>
                    </div>
                    <table class="info-table">
                        <tr>
                            <td>sku</td>
                            <td>KE-008819</td>
                        </tr>
                        <tr>
                            <td>category</td>
                            <td>Food</td>
                        </tr>
                        <tr>
                            <td>tags</td>
                            <td>Food, Fruits, Vegetables</td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import CustomRatioImg from "@/components/CustomRatioImg.vue"


export default {
    components: {
        CustomRatioImg
    },
    data: () => ({
        qty: 1
    })
}
</script>

<style>
.modal-wrapper{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 100;
    background: rgba(0, 0, 0, .5);
    display: flex;
    justify-content: center;
    padding: 5em 15%;
}
.modal{
    background-color: #fff;
    margin: auto;
    max-height: 100%;
    width: 100%;
    max-width: 1150px;
    padding: 3em;
    position: relative;
    border-radius: 10px;
    animation: pop .5s;
    overflow: auto;
}
.modal::-webkit-scrollbar {
    display: none;
}
.modal .modal-close{
    position: absolute;
    top: .2em;
    right: .4em;
    font-size: 1.5em;
    cursor: pointer;
    color: #666;
}

.modal-content{
    display: flex;
    justify-content: space-between;
}
.modal-content > div{
    width: 50%;
}
.modal-content .info{
    padding-left: 2.5em;
}

.preview-imgs{
    margin-top: 5%;
}
.preview-imgs > div{
    width: 17%;
}
.modal-content .img p{
    margin-top: 1em;
    color: #666;
    font-size: .9em;
    cursor: pointer;
}
.modal-content .img p span{
    text-decoration: underline;
    display: inline-block;
    margin-left: .5em;
}

.info .status{
    display: flex;
    align-items: center;
}
.status .status-text{
    text-transform: uppercase;
    color: #BDBDBD;
}
.status .status-value{
    color: #219653;
    font-size: .85em;
    display: inline-block;
    margin-left: 2em;
}
.info .product-name{
    font-size: 1.5em;
    font-weight: 500;
    margin: .5em 0;
}
.info .rating{
    font-size: .85em;
    color: #FABE50;
}
.info .rating span{
    color: #4F4F4F;
}

.info .price{
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    margin-top: .5em;
}
.info .price span{
    margin-left: 1em;
}
.info .price span:first-child{
    margin-left: 0;
}
.info .price .current{
    font-size: 2em;
    font-weight: 600;
    color: #333;
}
.info .price .previous{
    font-size: 1.5em;
    color: #828282;
    text-decoration: line-through;
}
.info .price .vat{
    font-size: .9em;
    color: #828282;
}
.info .sell-count{
    color: #4F4F4F;
    border-bottom: 1px solid #E0E0E0;
    margin-top: 1em;
    padding-bottom: 1em;
}

.info .qty-ctrl{
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 1em;
}
.qty-ctrl .qty-label{
    text-transform: uppercase;
    color: #4F4F4F;
}
.qty-ctrl .qty-stock{
    font-size: .9em;
    color: #828282;
}
.qty-ctrl-wrapper{
    display: flex;
    align-items: center;
    margin: 0 1.5em;
}
.qty-ctrl-wrapper .qty-btn{
    width: 60px;
    height: 60px;
    border: 1px solid #BDBDBD;
    background: transparent;
    border-radius: 50%;
    color: #0D0D0D;
    font-size: 1.5em;
}
.qty-ctrl-wrapper .qty-btn.num{
    background: #F2F2F2;
    border: none;
    margin: 0 .75em;
    cursor: initial;
}
.info .btn{
    margin-top: 1em;
}
.info .btn.buy-now{
    background-color: #F2F2F2;
    color: #4F4F4F;
    font-weight: 600;
}
.info .nav{
    margin-top: 1.25em;
    color: #4F4F4F;
    flex-wrap: wrap;
    border-bottom: 1px solid #E0E0E0;
    padding-bottom: 1em;
}
.info .nav .nav-item{
    margin: .25em 0;
    cursor: pointer;
}
.nav-item i{
    display: inline-block;
    margin-right: .5em;
}

.info-table{
    margin-top: 1.5em;
}
.info-table td{
    padding-bottom: 1em;
}
.info-table tr td:first-child{
    width: 7em;
    color: #BDBDBD;
    text-transform: uppercase;
}
.info-table tr td:nth-child(2){
    color: #4F4F4F;
    font-weight: 500;
}
</style>