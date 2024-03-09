<template>
  <div class="layout">
    <Header></Header>
    <Main></Main>
    <Footer></Footer>
    <img src="../assets/bg.png" alt="" />
  </div>
</template>
<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import Main from "../components/Main.vue";
</script>
<style scoped lang="less">
.layout {
  width: 1920px;
  height: 1080px;

  // z-index: 500;
  position: relative;
  img {
    // position: ab;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
  }
}
</style>
