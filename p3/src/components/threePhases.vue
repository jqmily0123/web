<template>
  <div class="three_phases">
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
.three_phases {
  width: 807px;
  height: 768px;
  position: relative;
  .circle {
    position: absolute;
    left: 0;
    top: 0;
  }
  :nth-child(1) {
    top: 519px;
    left: -5px;
    //border:1px solid red;
  }
  :nth-child(2) {
    top: 518px;
    left: 222px;
    //border:1px solid red;
  }
  :nth-child(3) {
    top: 518px;
    left: 460px;
    //border:1px solid red;
  }
  :nth-child(4) {
    top: 630px;
    left: 14px;
    //border:1px solid red;
  }
  :nth-child(5) {
    top: 636px;
    left: 224px;
    //border:1px solid red;
  }
  :nth-child(6) {
    top: 636px;
    left: 461px;
    //border:1px solid red;
  }
}
</style>
