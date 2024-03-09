<template>
  <div class="header">
    <div class="title">船闸人字门在线监测及健康诊断系统</div>
    <div class="subtitle"></div>
  </div>
</template>
<script setup></script>
<style scoped lang="less">
.header {
  height: 100px;
  font-size: 38px;
  font-weight: 700;
  color: #fff;
  display: flex;
  justify-content: center;
  background-image: url(../assets/header.svg);
  position: relative;
  z-index: 2;
  .title {
    position: absolute;
    top: 15px;
  }
  .subtitle {
    width: 300px;
    height: 219px;
    background: url(../assets/subtitle.svg) no-repeat;
    position: absolute;
    left: 10px;
    top: 40px;
  }
}
</style>
