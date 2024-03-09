<template>
  <div class="singleBox">
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
  // border: 1px solid red;
  position: relative;
  margin-top: 104px;
  .circle {
    position: absolute;
    // top: 0;
    right: 322px;
  }
  :nth-child(1) {
    top: 12px;
    right: 317px;
  }
  :nth-child(2) {
    bottom: 66px;
    right: 316px;
  }
}
</style>
