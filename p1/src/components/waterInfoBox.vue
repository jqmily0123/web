<template>
  <div class="waterinfo">
    <div class="outIcon">
      <div class="innerIcon" :id="uid"></div>
      <div class="center">
        <div class="cicon">
          <img src="../assets/水源.png" alt="" />
        </div>
      </div>
      <div class="ctext">{{ ctext }}</div>
    </div>
    <div class="box">
      <div class="high">
        <div class="data">{{ highData }}</div>
        <div class="dec">{{ highDec }}</div>
      </div>
    </div>
    <div class="box">
      <div class="low">
        <div class="data">{{ lowData }}</div>
        <div class="dec">{{ lowDec }}</div>
      </div>
    </div>
    <div class="chart">
      <img src="../assets/折线.png" alt="" />
    </div>
  </div>
</template>
<script setup>
import { v4 as uuidv4 } from "uuid";
import { onMounted } from "vue";
const uid = uuidv4();
let rotateTimes = 1;
onMounted(() => {
  const dom = document.getElementById(uid);
  setInterval(() => {
    dom.style.transform = "rotateZ(" + 10 * rotateTimes + "deg)";
    rotateTimes++;
  }, 100);
});

const props = defineProps({
  highData: {
    type: String,
  },
  highDec: {
    type: String,
  },
  lowData: {
    type: String,
  },
  lowDec: {
    type: String,
  },
  ctext: {
    type: String,
  },
});
// xuanzhuan;
</script>
<style scoped lang="less">
.waterinfo {
  width: 462px;
  height: 160px;
  background-image: url(../assets/bg1.png);
  display: flex;
  flex-wrap: wrap;
  position: relative;
  margin-top: 8px;
  box-sizing: border-box;
  padding-top: 15px;
  overflow: hidden;
  .outIcon {
    width: 90px;
    height: 90px;
    background-image: url(../assets/椭圆形.png);
    // background-color: red;
    margin-left: 30px;
    position: relative;

    .center {
      width: 32px;
      height: 32px;

      position: absolute;
      left: 50%;
      top: 37%;
      transform: translate(-50%, -50%);
    }
    .ctext {
      color: #66ffff;
      font-size: 14px;
      width: 90px;
      position: absolute;
      text-align: center;
      left: 50%;
      top: 62%;
      transform: translate(-50%, -50%);
    }
    .innerIcon {
      width: 100%;
      height: 100%;

      background-image: url(../assets/位图.png);
      z-index: 1000;
      //   background-color: green;
    }
  }
  .box {
    height: 90px;
    display: flex;
    align-items: center;
    .high,
    .low {
      width: 138px;
      height: 44px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      .data {
        font-size: 19px;
      }
      .dec {
        color: white;
        font-size: 14px;
      }
    }
    .high {
      margin-left: 30px;
      .data {
        color: #66ffff;
      }
    }
    .low {
      .data {
        color: #fedb65;
      }
    }
  }
  .chart {
    position: absolute;
    bottom: -10px;
    left: 0px;
  }
}
</style>
