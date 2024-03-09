<template>
  <div class="footer">
    <div class="footer_button_list">
      <Footerbutton
        class="footer_button"
        v-for="(item, index) in buttons"
        :key="index"
        :iconDec="item.iconDec"
      >
        <img :src="item.iconSrc" class="img" />
      </Footerbutton>
    </div>
  </div>
</template>
<script setup>
import Footerbutton from "./Footerbutton.vue";
const buttons = [
  { iconSrc: "../../public/fIcon1.svg", iconDec: "首页" },
  { iconSrc: "../../public/fIcon2.svg", iconDec: "功能" },
  { iconSrc: "../../public/fIcon3.svg", iconDec: "帮助" },
  { iconSrc: "../../public/fIcon4.svg", iconDec: "关于" },
  { iconSrc: "../../public/fIcon5.svg", iconDec: "设置" },
];
</script>
<style scoped lang="less">
.footer {
  width: 100%;
  height: 110px;
  margin-top: 80px;
  display: flex;
  justify-content: center;
  position: relative;
}
.footer_button_list {
  // margin-bottom: 20px;
  position: absolute;
  bottom: -750px;
  margin: -20px;
  width: 450px;
  height: 100%;
  // background-color: red;
  display: flex;
  justify-content: space-between;
  z-index: 2;
  .img {
    width: 70px;
    height: 70px;
  }
}
</style>
