<template>
  <div id="app">
    <Sidebar />
    <div class="main">
      hello
    </div>
  </div>
</template>

<script>
import Sidebar from "@/components/Sidevar.vue"

export default {
  name: 'App',
  components: {
    Sidebar
  }
}
</script>


<style>
#app{
  display: flex;
}
.sidebar{
  background: red;
  width: 23.65%;

}
.main{
  background: green;
  flex-grow: 1;
  margin-left: 1.8%;
}
</style>