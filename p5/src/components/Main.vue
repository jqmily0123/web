<template>
  <div class="main">
    <div class="left_button"></div>
    <div class="pagebox" v-if="pageButton">
      <PageButton
        v-for="(item, index) in pageButton"
        :key="index"
        v-bind="item"
        @click="handleClick(item.url)"
      >
        <img :src="item.iconSrc" />
      </PageButton>

      <!-- <img src="../assets/center.png" alt="" /> -->
    </div>
    <div class="right_button"></div>
  </div>
</template>
<script setup>
import PageButton from "./PageButton.vue";
const pageButton = [
  {
    title: "工作台",
    iconSrc: "../../public/icon1.svg",
    url: "",
  },
  {
    title: "沭新河南</br>船闸人字门</br>概况",
    iconSrc: "../../public/icon2.svg",
    url: "http://127.0.0.1:8081/",
  },
  {
    title: "船闸人字门</br>现场测点布置方案",
    iconSrc: "../../public/icon5.svg",
    url: "http://127.0.0.1:8083/",
  },
  {
    title: "船闸人字门</br>智能在线监测</br>系统",
    iconSrc: "../../public/icon4.svg",
    url: "http://127.0.0.1:8084/",
  },
  {
    title: "船闸人字门</br>智慧健康诊断</br>系统",
    iconSrc: "../../public/icon3.svg",
    url: "http://127.0.0.1:8082/",
  },
];
const handleClick = (url) => {
  window.location.href = url;
};
</script>
<style scoped lang="less">
.main {
  width: 100%;
  height: 700px;
  margin-top: 100px;
  box-sizing: border-box;
  background-position: center;
  display: flex;
  align-content: center;
  justify-content: center;
  position: absolute;
  letter-spacing: 3px;
  background: url(../assets/center.png) no-repeat center;
  z-index: 2;
  // border: 1px solid red;
  .pagebox {
    display: flex;
    align-items: center;
  }

  // img {
  //   position: relative;
  //   top: 0;
  //   left: 0;
  // }
  .left_button,
  .right_button {
    position: absolute;
    top: 251px;
    width: 58px;
    height: 180px;
    z-index: 2;
    // background-color: red;
  }
  .left_button {
    background-image: url(../assets/leftButton.svg);
    left: 100px;
    // margin-right: 150px;
  }
  .right_button {
    background-image: url(../assets/rightButton.svg);
    right: 100px;
    // margin-left: 150px;
  }
}
</style>
