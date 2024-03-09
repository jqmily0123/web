<template>
  <div class="page_button">
    <div class="icon">
      <slot></slot>
    </div>
    <div class="title">
      <div v-html="title"></div>
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  bgSrc: {
    type: String,
  },
  iconSrc: {
    type: String,
  },
  title: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.page_button {
  width: 230px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url(../assets/pagebox_bg.svg) no-repeat -19px center;
  // background-color: red;
  // border: 1px solid red;
  position: relative;
  z-index: 1000;
  .icon {
    width: 24px;
    height: 24px;
    position: absolute;
    top: 75px;
    left: 70px;
  }
  .title {
    width: 180px;
    height: 128px;
    font-size: 25px;
    color: #00e2ff;
    text-indent: 2.2px;
    text-align: center;
    // line-height: 128%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
    font-weight: 700;
    letter-spacing: 4px;
  }
}
</style>
