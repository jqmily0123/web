<template>
  <div class="container">
    <div class="title">{{ title }}</div>
    <div class="title">{{ subtitle }}</div>
    <div class="data" >
      <span>{{ data }}%</span>
      <div class="svg">
        <svg width="81" height="59" viewBox="0 0 81 59" fill="none">
          <g opacity="1" transform="translate(0 0)  rotate(0)">
            <path
              id="椭圆形 (轮廓)"
              fill-rule="evenodd"
              :fill="uuList2[0]"
              opacity="0.8"
              d="M40.5,3c22.36,0 40.5,12.54 40.5,28c0,15.46 -18.14,28 -40.5,28c-22.36,0 -40.5,-12.54 -40.5,-28c0,-15.46 18.14,-28 40.5,-28zM67.69,13.29c-7.48,-5.16 -16.54,-7.75 -27.19,-7.75c-10.65,0 -19.71,2.59 -27.19,7.75c-7.18,4.97 -10.77,10.87 -10.77,17.71c0,6.84 3.59,12.74 10.77,17.71c7.48,5.16 16.54,7.75 27.19,7.75c10.65,0 19.71,-2.59 27.19,-7.75c7.18,-4.97 10.77,-10.87 10.77,-17.71c0,-6.84 -3.59,-12.74 -10.77,-17.71z"
            ></path>
            <path
              id="椭圆形 (轮廓)"
              fill-rule="evenodd"
              :fill="uuList2[1]"
              opacity="0.8"
              d="M40.5,11c16.84,0 30.5,8.28 30.5,18.5c0,10.22 -13.66,18.5 -30.5,18.5c-16.84,0 -30.5,-8.28 -30.5,-18.5c0,-10.22 13.66,-18.5 30.5,-18.5zM59.43,20.76c-5.15,-3.12 -11.46,-4.68 -18.93,-4.68c-7.47,0 -13.78,1.56 -18.93,4.68c-4.32,2.63 -6.49,5.54 -6.49,8.74c0,3.2 2.17,6.11 6.49,8.74c5.15,3.12 11.46,4.68 18.93,4.68c7.47,0 13.78,-1.56 18.93,-4.68c4.32,-2.63 6.49,-5.54 6.49,-8.74c0,-3.2 -2.17,-6.11 -6.49,-8.74z"
            ></path>

          </g>
          <defs>
            <linearGradient
              :id="uuList[0]"
              x1="50%"
              y1="0%"
              x2="51%"
              y2="100%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" :stop-color="stopColor1" stop-opacity="1" />
              <stop offset="1" :stop-color="stopColor2" stop-opacity="1" />
            </linearGradient>
            <linearGradient
              :id="uuList[1]"
              x1="50%"
              y1="0%"
              x2="51%"
              y2="100%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" :stop-color="stopColor1" stop-opacity="1" />
              <stop offset="1" :stop-color="stopColor2" stop-opacity="1" />
            </linearGradient>
            <linearGradient
              :id="uuList[2]"
              x1="50%"
              y1="0%"
              x2="51%"
              y2="100%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" :stop-color="stopColor2" stop-opacity="1" />
              <stop offset="1" :stop-color="stopColor1" stop-opacity="1" />
            </linearGradient>
          </defs>
        </svg>
      </div>
    </div>
  </div>
</template>

<script setup>
import { v4 as uuidv4 } from "uuid";
// import { toRaw } from "vue";
const props = defineProps({
  title: {
    type: String,
  },
  subtitle: {
    type: String,
  },
  data: {
    type: String,
  },
  stopColor1: {
    type: String,
  },
  stopColor2: {
    type: String,
  },
  stopColor3: {
    type: String,
  },
  color: {
    type: String,
  },
});
// console.log(uuidv4());
const uuList = [uuidv4(), uuidv4(), uuidv4()];
const uuList2 = uuList.map((item) => `url(#${item})`);
</script>
<style scoped lang="less">
.container {
  width: 134px;
  height: 125px;
  display: flex;
  flex-direction: column;
  align-items: center;
  //   background-color: red;
  .title {
    color: #efefef;
    font-size: 18px;
    margin-bottom: 10px;
    z-index: 1000;
  }
  .data {
    // color: #f7b1a3;
    width: 82px;
    height: 60px;
    font-size: 12px;

    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    .svg {
      position: absolute;
      top: 0;
      left: 0;
    }
    span {
      display: inline-block;
      color: white;
      height: 100%;
      width: 100%;
      font-size: 15px;
      line-height: 60px;
      text-align: center;
      z-index: 2;
    }
  }
}
</style>
