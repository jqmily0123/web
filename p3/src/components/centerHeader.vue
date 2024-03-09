<template>
  <div class="center-header">
    <img src="../assets/centerHeader.svg" alt="" class="img" />
    <div class="text">布置方案</div>
    <div class="tip">
      提示：
      <br />
      <div class="dec">
        点击图中传感器红色标识可
        <br />
        显示对应传感器参数及布置情况。
      </div>
    </div>
  </div>
</template>

<script setup></script>
<style scoped lang="less">
.center-header {
  // position: absolute;
  position: relative;
  height: 100px;
  display: flex;
  flex-direction: column;
  align-items: center;
  // background-color: red;
  .img {
    position: absolute;
    top: -200px;
  }
  .text {
    width: 100%;
    // background-color: red;
    position: absolute;
    bottom: 20px;
    color: #00fff4;
    font-size: 16px;
    // border: 1px solid red;
    text-align: center;
    font-weight: 700;
    letter-spacing: 2px;
  }
  .tip {
    // border: 1px solid red;
    width: 290px;
    color: #fff;
    font-size: 18px;
    position: absolute;
    bottom: 10px;
    right: 0;
    text-align: left;
    opacity: 0.8;
    line-height: 20px;
    font-weight: 700;
    .dec {
      text-indent: 2em;
      line-height: 24px;
      letter-spacing: 1px;
    }
  }
}
</style>
