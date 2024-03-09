<template>
  <div class="left1">
    <bgBox v-bind="left1" class="box1">
      <swiper
        :space-between="50"
        class="inner"
        v-bind="swiperData"
      >
        <swiper-slide v-for="item in left1.showList" :key="item.id">
          <img :src="item.tImage" alt="" class="image image1" />
          <div>{{ item.title }}</div>
          <img :src="item.bImage" alt="" class="image image2" />
          <div>{{ item.dec }}</div>
        </swiper-slide>
      </swiper>
    </bgBox>
    <bgBox v-bind="left2" class="box2">
      <img src="../assets/left2.png" alt="" />
    </bgBox>
  </div>
</template>

<script setup>
import bgBox from "./bgBox.vue";
import { Swiper, SwiperSlide, useSwiper } from "swiper/vue";
import { Autoplay, Pagination, Navigation } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";
const modules = [Autoplay, Pagination, Navigation];
import { reactive, ref } from "vue";

const left1 = {
  title: "传感器实物图与链接方式",
  width: "440px",
  height: "502px",

  whichbg: "1",
  showList: [
    {
      id: 1,
      title: "单向加速度传感器实物图",
      dec: "单向加速度传感器连接方式",
      tImage: "../public/lt1.png",
      bImage: "../public/lb1.png",
    },
    {
      id: 2,
      title: "倾角传感器实物图",
      dec: "倾角传感器连接方式",
      tImage: "../public/lt2.png",
      bImage: "../public/lb2.png",
    },
    {
      id: 3,
      title: "三向加速度传感器实物图",
      dec: "三向加速度传感器连接方式",
      tImage: "../public/lt3.png",
      bImage: "../public/lb3.png",
    },
    {
      id: 4,
      title: "表面式应变计实物图",
      dec: "表面式应变计连接方式",
      tImage: "../public/lt4.png",
      bImage: "../public/lb4.png",
    },
  ],
};
const left2 = {
  title: "船闸监测点布置优化流程",
  width: "440px",
  height: "331px",
  whichbg: "2",
};

// const swiper = ref({});
const swiperData = reactive({
  autoplay: {
    delay: 2500,
    disableOnInteraction: false,
    pauseOnMouseEnter: true,
  },
  modules: modules,
  navigation: true,
  centeredSlides: true,
  loop: true,
});
</script>
<style scoped lang="less">
.left1 {
  width: 440px;
  z-index: 2;
  position: relative;

  .box1 {
    width: 100%;
    // // position: absolute;

    .inner {
      width: 400px;
      height: calc(100% - 80px);
      position: absolute;
      top: 50px;
      color: white;
      text-align: center;
      font-size: 20px;
      display: flex;
      flex-wrap: nowrap;
      // border: 1px solid red;
      background: linear-gradient(rgba(9, 210, 197), rgba(0, 48, 143));

      :deep(.swiper-button-prev),
      :deep(.swiper-button-next) {
        color: skyblue;
        opacity: 0.3;
      }
      :deep(.swiper-button-prev:after),
      :deep(.swiper-button-next:after) {

        font-size: 30px;

      }
      :deep(.swiper-wrapper) {
        .image1 {
          height: 175px;
          // border: 1px solid red;
        }
        .image2 {
          margin-top: 10px;
          // border: 1px solid red;
          height: 160px;
        }
      }
    }
  }
  .box2 {
    margin-top: 40px;
    img {
      top: 40px;
      position: absolute;
    }
  }
}
</style>
