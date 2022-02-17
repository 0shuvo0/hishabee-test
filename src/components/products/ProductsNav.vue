<template>
    <div class="products-nav flex-center flex-wrap">
        <div class="categories">
            <span>Fruits</span>
            <span>Green Fruits</span>
            <span class="active">Fresh Fruits</span>
        </div>
        <div class="controls">
            <span>
                <b>20</b> Products Found
            </span>
            <span>
                <i class="bi-list-ul"></i>
            </span>
            <span>
                <i class="bi-grid-3x3-gap-fill"></i>
            </span>
            <span>
                Default Sorting
                <i class="bi-chevron-down"></i>
            </span>
        </div>
    </div>
</template>

<style>
.products-nav > div{
    margin-bottom: 1em;
}
.products-nav span{
    cursor: pointer;
}
.products-nav .categories span{
    display: inline-block;
    font-size: 1em;
    color: #828282;
    padding: 0;
    padding: 0 1.5em;
    position: relative;
}
.categories span.active{
    color: #333333;
    font-weight: 500;
}
.categories span::after{
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    height: 70%;
    width: 2px;
    background-color: #828282;
}
.categories span:first-child{
    padding-left: 0;
}
.categories span:first-child::after{
    display: none;
}

.products-nav .controls{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.controls span{
    margin-right: 1.5em;
    font-size: 1em;
    color: #828282;
}
.controls span:last-child{
    margin-right: 0;
}
.controls span b{
    color: #333333;
}
</style>