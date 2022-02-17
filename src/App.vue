<template>
  <div id="app">
    <Sidebar />
    <div class="main">
      <div class="hero-img">
        <CustomRatioImg :src="heroImg" pt="23.5%" />
      </div>
      <ProductsSection />
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/sidebar/Sidevar.vue"
import CustomRatioImg from "@/components/CustomRatioImg.vue"
import heroImg from "@/assets/img/hero bg.png"
import ProductsSection from "@/components/products/ProductsSection.vue"

export default {
  name: 'App',
  components: {
    Sidebar,
    CustomRatioImg,
    ProductsSection
  },
  data: () => ({
    heroImg
  })
}
</script>


<style>
#app{
  display: flex;
}
.sidebar{
  min-width: 23.65%;

}
.main{
  flex-grow: 1;
  margin-left: 1.8%;
}

.hero-img{
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.02);
  margin-bottom: 2em;
}
</style>