<template>
  <div class="center">
    <div class="png1">
      <img src="../assets/c3.png" alt="" />
    </div>
    <div class="png2">
      <img src="../assets/c1.svg" alt="" />
    </div>
    <div class="png3">
      <cube-box></cube-box>
    </div>
  </div>
</template>
<script setup>
import cubeBox from "./cubeBox.vue";
</script>
<style scoped lang="less">
.center {
  width: 1030px;
  height: 1000px;

  background-image: url(../assets/c2.png);
  background-position: center center;
  background-repeat: no-repeat;
  position: relative;
  .png1,
  .png2,
  .png3 {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: 44px;
    background-position: center center;
    background-repeat: no-repeat;
    // background-color: red;
  }
  .png3 {
    position: absolute;
    top: 360px;
  }
  .png2 {
    position: absolute;
    top: 60px;
  }
  .png3 {
    //border: 1px solid red ;
    height: 500px;
    background-image: url(../assets/c5.png);
    //z-index: 1000;
  }
}
</style>
