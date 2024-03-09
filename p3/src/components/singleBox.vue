<template>
  <div class="singleBox">
    <circleBox class="circle"></circleBox>
    <circleBox class="circle"></circleBox>
    <circleBox class="circle"></circleBox>
    <circleBox class="circle"></circleBox>
    <circleBox class="circle"></circleBox>
    <circleBox class="circle"></circleBox>
  </div>
</template>

<script setup>
import circleBox from "./circleBox.vue";
</script>
<style scoped lang="less">
.singleBox {
  width: 807px;
  height: 768px;
  position: relative;
  margin-top: 104px;
  .circle {
    position: absolute;
    //top: 0;
    top: 13px;
  }
  :nth-child(2) {
    left: 229px;
  }
  :nth-child(3) {
    left: 451px;
  }
  :nth-child(n + 4) {
    top: 678px;
  }
  :nth-child(4) {
    left: 223px;
    top: 675px;
  }
  :nth-child(5) {
    left: 455px;
    top: 678px;
  }
}
</style>
