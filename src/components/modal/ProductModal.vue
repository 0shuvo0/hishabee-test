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
                    info
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
    }
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
</style>