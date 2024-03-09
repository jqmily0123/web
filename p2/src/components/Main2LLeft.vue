<template>
  <div class="container">
    <div class="m-left">
      <div class="content">
        <Title title="健康诊断情况"></Title>
        <subTitle :currentTime="currentTime" text="检测概况"></subTitle>
        <div class="health-box">
          <Health v-bind="healthData1" class="health"></Health>
          <Health v-bind="healthData2" class="health"></Health>
        </div>
      </div>
      <div class="bg">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="405.00048828125"
          height="711"
          viewBox="0 0 405.00048828125 711"
          fill="none"
        >
          <g opacity="1" transform="translate(0 0)  rotate(0)">
            <g id="矩形" filter="url(#filter_1)">
              <path
                id="矩形"
                fill-rule="evenodd"
                style="fill: #0b1033"
                opacity="1"
                d="M0 711L405 683.98L405 35.12L0 0L0 711Z"
              ></path>
            </g>
            <g id="矩形 (轮廓)" filter="url(#filter_42)">
              <path
                id="矩形 (轮廓)"
                fill-rule="evenodd"
                fill="url(#linear_43)"
                opacity="1"
                d="M405,683.98l-405,27.02v-711l405,35.12zM399,40.62l-393,-34.08v698.05l393,-26.22z"
              ></path>
            </g>
            <path
              id="矩形"
              fill-rule="evenodd"
              fill="url(#linear_43)"
              opacity="1"
              d="M388.881 494.146L405.001 494.146L405.001 225.486L388.881 225.486L388.881 494.146Z"
            ></path>
          </g>
          <defs>
            <filter
              id="filter_1"
              x="-34"
              y="-34"
              width="473"
              height="779"
              filterUnits="userSpaceOnUse"
              color-interpolation-filters="sRGB"
            >
              <feFlood flood-opacity="0" result="feFloodId" />
              <feColorMatrix
                in="SourceAlpha"
                type="matrix"
                values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
                result="hardAlpha"
              />

              <feOffset dx="0" dy="0" />
              <feGaussianBlur stdDeviation="17" />
              <feComposite
                in2="hardAlpha"
                operator="arithmetic"
                k2="-1"
                k3="1"
              />
              <feColorMatrix
                type="matrix"
                values="0 0 0 0 0.0392156862745098 0 0 0 0 0.07450980392156863 0 0 0 0 0.6627450980392157 0 0 0 1 0"
              />
              <feBlend
                mode="normal"
                in2="filter_feFlood"
                result="filter_feFlood_1"
              />
              <feBlend
                mode="normal"
                in="SourceGraphic"
                in2="filter_1"
                result="shape"
              />
            </filter>
            <linearGradient
              id="linear_43"
              x1="92.11858526584251%"
              y1="49.99999999999998%"
              x2="0%"
              y2="49.99999999999998%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" stop-color="#0B44B5" stop-opacity="1" />
              <stop
                offset="0.3784117641270185"
                stop-color="#0E5FFF"
                stop-opacity="1"
              />
              <stop offset="1" stop-color="#0E5FFF" stop-opacity="0" />
            </linearGradient>
            <filter
              id="filter_42"
              x="-34"
              y="-34"
              width="473"
              height="779"
              filterUnits="userSpaceOnUse"
              color-interpolation-filters="sRGB"
            >
              <feFlood flood-opacity="0" result="feFloodId" />
              <feColorMatrix
                in="SourceAlpha"
                type="matrix"
                values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
                result="hardAlpha"
              />

              <feOffset dx="0" dy="0" />
              <feGaussianBlur stdDeviation="17" />
              <feComposite
                in2="hardAlpha"
                operator="arithmetic"
                k2="-1"
                k3="1"
              />
              <feColorMatrix
                type="matrix"
                values="0 0 0 0 0.0392156862745098 0 0 0 0 0.07450980392156863 0 0 0 0 0.6627450980392157 0 0 0 1 0"
              />
              <feBlend
                mode="normal"
                in2="filter_feFlood"
                result="filter_feFlood_1"
              />
              <feBlend
                mode="normal"
                in="SourceGraphic"
                in2="filter_42"
                result="shape"
              />
            </filter>
            <linearGradient
              id="linear_44"
              x1="72.0290406174854%"
              y1="0%"
              x2="72.02904061748185%"
              y2="100.00000000000071%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" stop-color="#3D7FFF" stop-opacity="0" />
              <stop
                offset="0.4996258762766419"
                stop-color="#3C7DFC"
                stop-opacity="1"
              />
              <stop offset="1" stop-color="#3D7FFF" stop-opacity="0" />
            </linearGradient>
          </defs>
        </svg>
      </div>
    </div>
    <div class="b-left">
      <subTitle
        :currentTime="currentTime"
        text="诊断情况"
        class="sub"
      ></subTitle>
      <div class="databoxs">
        <dataBox class="item" v-bind="mockData[0]"></dataBox>
        <dataBox class="item" v-bind="mockData[1]"></dataBox>
        <dataBox class="item" v-bind="mockData[2]"></dataBox>
        <dataBox class="item" v-bind="mockData[3]"></dataBox>
      </div>
    </div>
  </div>
</template>

<script setup>
import dayjs from "dayjs";
import { ref } from "vue";
import Health from "./Health.vue";
import subTitle from "./subTitle.vue";
import dataBox from "./dataBox.vue";
import Title from "./Title.vue";
const healthData1 = ref({});
const dat = new Date();
healthData1.value = {
  title: "健康[A]",
  subtitle: "概率赋值",
  date: `${dat.getMonth()+1}月`,
  dec: "本月情况",
  data: "99.99%",
};
const healthData2 = ref({});
healthData2.value = {
  title: "健康[A]",
  subtitle: "概率赋值",
  date: "2023年",
  dec: "本年情况",
  data: "99.99%",
};
const date = ref();
const currentTime = ref();
setInterval(() => {
  date.value = new Date();
  currentTime.value = dayjs(date.value).format("YY-MM-DD HH:mm:ss");
}, 1000);
// console.log(currentTime.value);
const mockMathdata = () => {
  return (Math.random() * 10 + 90).toFixed(2);
};
const getmockMathdata = () => {
  return [
    {
      title: "应变检测数据健康赋值",
      data: `${mockMathdata()}%`,
      png: "../../public/2.png",
    },
    {
      title: "应力检测数据健康赋值",
      data: `${mockMathdata()}%`,
      png: "../../public/2.png",
    },
    {
      title: "振动检测数据健康赋值",
      data: `${mockMathdata()}%`,
      png: "../../public/2.png",
    },
    {
      title: "倾角检测数据健康赋值",
      data: `${mockMathdata()}%`,
      png: "../../public/2.png",
    },
  ];
};
const mockData = ref({});
mockData.value = getmockMathdata();
setInterval(() => {
  mockData.value = getmockMathdata();
}, 3000);
</script>
<style scoped lang="less">
.container {
  // background-color: red;
  width: 350px;
  position: relative;
  .m-left {
    height: 295px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    // padding-top: 50px;
    .bg {
      top: 0;
      left: 0;
      position: absolute;
      // background-color: pink;
    }
    .content {
      z-index: 2;
      display: flex;
      flex-direction: column;
      // background-color: red;
      .title {
        font-size: 22px;
        font-weight: 600;
        color: white;
        text-align: center;
      }

      .health-box {
        display: flex;
        justify-content: space-around;
      }
    }
  }
  .b-left {
    width: 100%;
    height: 246px;
    box-sizing: border-box;
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .sub {
      padding: 0 40px 0 20px;
    }
    .databoxs {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      padding: 0 20px;
      .item {
        width: 170px;
        height: 88px;
        margin-bottom: 20px;
        // background-color: green;
      }
    }
  }
}
</style>
