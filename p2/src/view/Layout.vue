<template>
  <div class="layout">
    <div class="title">
      <titleL></titleL>
    </div>
    <div class="main1">
      <Main1L></Main1L>
    </div>
    <div class="main2">
      <Main2L></Main2L>
    </div>
    <div class="foot">
      <img src="../assets/4.png" alt="" />
    </div>
  </div>
</template>

<script setup>
import TitleL from "../components/TitleL.vue";
import Main1L from "../components/Main1L.vue";
import Main2L from "../components/Main2L.vue";
</script>
<style scoped lang="less">
.layout {
  width: 1920px;
  height: 1080px;
  // background-color: red;
  .title {
    width: 1921px;
    height: 86px;
  }
  .main1 {
    width: 100%;
    height: 188px;
    // background-color: red;
  }
  .foot {
    width: 100%;
    // background-color: red;
    display: flex;
    justify-content: center;
  }
}
</style>
