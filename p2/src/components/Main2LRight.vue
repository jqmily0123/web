<template>
  <div class="m-right">
    <div class="bg">
      <img src="../assets/6.png" alt="" />
    </div>
    <div class="title">
      <Title title="总体船闸人字门综合健康诊断"></Title>
    </div>
    <div class="pie">
      <pieChart></pieChart>
    </div>
  </div>
</template>

<script setup>
import Title from "./Title.vue";
import pieChart from "./PieChart.vue";
</script>
<style scoped lang="less">
.m-right {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  .bg {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
  }
  .title {
    z-index: 1000;
  }
  .pie {
    width: 300px;
    height: 500px;
    //z-index: 1000;
    // background-color: red;
    display: flex;
    flex-direction: column;
    // justify-content: center;
    align-items: center;
    //border: 1px solid red;
  }
}
</style>
