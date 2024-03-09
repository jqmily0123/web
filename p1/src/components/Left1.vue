<template>
  <div class="left1">
    <subTitle title="下闸首人字门概况"></subTitle>
    <ul class="infolist">
      <li
        class="item"
        v-for="item in DataList"
        :key="item.id"
        :style="{
          backgroundImage: `url(${item.bgcUrl})`,
        }"
      >
        <!-- {{ item.bgcUrl }} -->
        <div class="data">{{ item.data }}</div>
        <div class="unit">{{ item.unit }}</div>
      </li>
    </ul>
    <waterInfoBox v-bind="waterInfoList[0]" class="wib"></waterInfoBox>
    <waterInfoBox v-bind="waterInfoList[1]" class="wib"></waterInfoBox>
  </div>
</template>
<script setup>
import subTitle from "./subTitle.vue";
import { v4 as uuidv4 } from "uuid";
import waterInfoBox from "./waterInfoBox.vue";
import { ref } from "vue";

const getMockData = () => {
  return (Math.random() * 10 + 10).toFixed(2);
};
const getDataList = () => {
  return [
    {
      id: uuidv4(),
      bgcUrl: "../../public/1.png",
      data: 11.48,
      unit: "高/m",
    },
    {
      id: uuidv4(),
      bgcUrl: "../../public/2.png",
      data: getMockData(),
      unit: "上游水位/m",
    },
    {
      id: uuidv4(),
      bgcUrl: "../../public/3.png",
      data: getMockData(),
      unit: "下游水位/m",
    },
  ];
};
const DataList = ref({});
DataList.value = getDataList();

setInterval(() => {
  DataList.value = getDataList();
}, 3000 * 100);

//
const waterInfoList = [
  {
    highData: 11.10 ,
    highDec: "最高通航水位/m",
    lowData: 6.74 ,
    lowDec: "最低通航水位/m",
    ctext: "上游水位",
  },
  {
    highData: 7.91,
    highDec: "最高通航水位/m",
    lowData: 6.42,
    lowDec: "最低通航水位/m",
    ctext: "下游水位",
  },
];
</script>
<style scoped lang="less">
.left1 {
  width: 465px;
  height: 572px;

  background-image: url(../assets/矩形.png);
  .infolist {
    width: 100%;
    height: 130px;
    // background-color: red;
    display: flex;
    justify-content: space-between;
    .item {
      width: 130px;
      height: 130px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      .data {
        font-size: 30px;
      }
      .unit {
        font-size: 14px;
      }
    }
  }
  .wib {
    margin-top: 20px;
  }
}
</style>
