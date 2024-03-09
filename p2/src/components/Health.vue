<template>
  <div class="health">
    <div class="h-top">
      <span>
        {{ title }}
      </span>
      <div class="svg1">
        <svg
          width="180.627685546875"
          height="51.998779296875"
          viewBox="0 0 180 51"
          fill="none"
        >
          <g id="椭圆形" filter="url(#filter_51)">
            <path
              id="椭圆形"
              fill-rule="evenodd"
              style="fill: #09d8ec"
              opacity="0.7"
              d="M163.869 25.9988C163.869 20.8988 130.929 16.7589 90.3088 16.7589C49.6988 16.7589 16.7588 20.8988 16.7588 25.9988C16.7588 31.0989 49.6988 35.2388 90.3088 35.2388C130.929 35.2388 163.869 31.0989 163.869 25.9988Z"
            ></path>
          </g>
          <defs>
            <filter
              id="filter_51"
              x="8.379378471381035"
              y="8.379439506537285"
              width="163.86402933743753"
              height="35.23993352597354"
              filterUnits="userSpaceOnUse"
              color-interpolation-filters="sRGB"
            >
              <feFlood flood-opacity="0" result="BackgroundImageFix" />
              <feBlend
                mode="normal"
                in="SourceGraphic"
                in2="BackgroundImageFix"
                result="shape"
              />
              <feGaussianBlur
                stdDeviation="4.189705295559483"
                result="effect1_foregroundBlur"
              />
            </filter>
          </defs>
        </svg>
      </div>
    </div>
    <div class="h-center">
      <div class="left">
        <div class="item1">
          <div class="sub-t">{{ subtitle }}</div>
          <div class="date">{{ date }}</div>
        </div>
        <div class="item2">
          {{ data }}
        </div>
      </div>
      <div class="right"></div>
    </div>
    <div class="h-bottom">
      <div class="text">{{ dec }}</div>
      <img src="../assets/1.png" alt="" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
  },
  subtitle: {
    type: String,
  },
  date: {
    type: String,
  },
  dec: {
    type: String,
  },
  data: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.health {
  display: flex;
  height: 144px;
  width: 168px;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  .h-top {
    height: 18px;
    width: 147px;
    color: white;
    line-height: 18px;
    position: relative;
    span {
      position: absolute;
      width: 100%;
      text-align: center;
      z-index: 2;
    }
    .svg1 {
      width: 100%;
      height: 100%;
      position: absolute;
      left: -18px;
      top: -18px;
    }
  }
  .h-center {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    // background-color: pink;
    .left {
      margin-top: 15px;
      .item1 {
        display: flex;
        // background-color: red;
        display: flex;
        justify-content: center;
        .sub-t {
          height: 18px;
          width: 53px;
          color: white;
          font-size: 12px;
          font-weight: 600;
        }
        .date {
          width: 41px;
          height: 18px;
          text-align: center;
          //color: rgb(32,170,17);
          background-image: linear-gradient(to right, orange, purple);
          -webkit-background-clip: text;
          color: transparent;
          font-weight: 700;
        }
      }
      .item2 {
        width: 188px;
        height: 28px;
        font-size: 22.5px;
        color: #75feff;
        text-align: center;
        line-height: 28px;
      }
    }
  }
  .h-bottom {
    width: 100%;
    height: 62px;
    // background-color: red;
    box-sizing: border-box;
    padding: 0px 10px;
    position: relative;
    line-height: 62px;
    text-align: center;
    img {
      position: absolute;
      left: 0;
      top: 0;
      z-index: -1;
    }
    .text {
      z-index: 1000;
      color: white;
      font-size: 13px;
      font-weight: 700;
      // background-color: red;
    }
  }
}
</style>
