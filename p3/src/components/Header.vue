<template>
  <div class="header">
    <img src="../assets/top.png" alt="" />
    <div class="text">船闸人字门现场测点布置方案</div>
    <div class="box">
      <div class="leftbox">
        <div class="dateBox">{{ date }}</div>
        <div class="weekBox">{{ week }}</div>
      </div>
      <div class="rightbox">
        <div class="projectBox">{{ project }}</div>
        <div class="infoBox">{{ info }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import dayjs from "dayjs";
const date = ref();
const week = ref();
const project = "沭新河南船闸下闸首闸门";
const info = "宿迁 . 阴天";
onMounted(() => {
  setInterval(() => {
    date.value = dayjs(new Date()).format("YYYY-MM-DD HH:mm:ss");
  }, 1000);
  // dayjs.extend(weekday);
  week.value = getWeek();
  setInterval(() => {
    week.value = getWeek();
  }, 1000 * 60 * 60 * 24);
});

const getWeek = () => {
  const dates = dayjs().day();
  const weeks = ["日", "一", "二", "三", "四", "五", "六"];
  return `星期${weeks[dates]}`;
};
</script>
<style scoped lang="less">
.header {
  width: 100%;
  height: 135px;
  z-index: 100;
  position: relative;

  .text {
    width: 100%;
    font-size: 40px;
    font-weight: 900;
    letter-spacing: 5px;
    color: rgba(255, 255, 255, 1);
    text-align: center;
    vertical-align: top;

    position: absolute;
    left: 0;
    top: 20px;
  }
  .box {
    width: 100%;
    display: flex;
    justify-content: space-between;
    position: absolute;
    top: 20px;
    left: 0;
    box-sizing: border-box;
    padding: 0 150px;
    color: #32c5ff;
    font-size: 16px;
    font-weight: 700;
    .leftbox,
    .rightbox {
      width: 300px;
      height: 92px;
      //   background-color: red;
      // border: 1px solid red;
      position: relative;
    }
    .dateBox {
      position: absolute;
      top: 40px;
      left: 30px;
    }
    .weekBox {
      position: absolute;
      top: 65px;
      right: 60px;
    }
    .projectBox {
      position: absolute;
      top: 40px;
      right: 20px;
    }
    .infoBox {
      position: absolute;
      top: 65px;
      left: 30px;
    }
  }
}
</style>
