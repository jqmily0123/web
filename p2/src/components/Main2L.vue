<template>
  <div class="m2">
    <Main2LLeft class="ml"></Main2LLeft>
    <Main2LCenter class="mc"></Main2LCenter>
    <Main2LRight class="mr"></Main2LRight>
  </div>
</template>

<script setup>
import Main2LLeft from "./Main2LLeft.vue";
import Main2LCenter from "./Main2LCenter.vue";
import Main2LRight from "./Main2LRight.vue";
</script>
<style scoped lang="less">
.m2 {
  display: flex;
  justify-content: space-around;
  .ml {
    width: 405px;
    height: 711px;
    // background-color: red;
  }
  .mc {
    width: 956px;
    height: 671px;
    // background-color: green;
  }

  .mr {
    width: 405px;
    height: 711px;
    // background-color: pink;
  }
}
</style>
