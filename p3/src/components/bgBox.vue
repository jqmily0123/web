<template>
  <div class="bgbox" :style="{ width, height }">
    <div class="title">{{ title }}</div>
    <div :class="[whichbg == 1 ? 'bg-long' : 'bg-short', 'bg']"></div>
    <div class="subtitle" v-if="subtitle">
      {{ subtitle }}
    </div>
    <Vue3SeamlessScroll
      :list="list"
      v-if="list"
      class="list"
      :class="{ right: !subtitle }"
      :hover=true
      :step=0.5
    >
      <div class="item" v-for="(item, index) in list" :key="index">
        <span class="item1">
          <img src="../assets/icon.svg" alt="" />
        </span>
        <span class="item2">{{ item.name }}</span>
        <span class="item3"> {{ item.dec }}</span>
        <span class="item4" v-if="item.dec2">{{ item.dec2 }}</span>
      </div>
    </Vue3SeamlessScroll>
    <slot></slot>
  </div>
</template>

<script setup>
import { Vue3SeamlessScroll } from "vue3-seamless-scroll";

const props = defineProps({
  title: {
    type: String,
  },
  width: {
    type: String,
  },
  height: {
    type: String,
  },
  bgurl: {
    type: String,
  },
  whichbg: {
    type: String,
  },
  list: {
    type: Array,
  },
  subtitle: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.bgbox {

  z-index: 1;
  position: relative;
  justify-content: center;
  font-size: 16px;
  font-weight: 700;
  color: #19ecff;
  overflow: hidden;
  display: flex;
  justify-content: center;

  .title {
    position: absolute;
    width: 100%;
    text-align: center;
    top: 5px;
    z-index: 100;
    color: #fff;
    letter-spacing: 2px;
  }
  .subtitle {
    width: 100%;
    height: 52px;
    position: absolute;
    top: 60px;
    left: 0;
    // background-color: red;
    color: #fff;
    line-height: 50px;
    text-align: center;
    background: url(../assets/subtitleBg.svg) no-repeat center;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 20px;
  }
  .bg {
    width: 100%;
    top: 0;
    left: 0;
  }
  .bg-long {
    // width: 440px;
    background: url("../../public/bg1.svg");
  }
  .bg-short {
    background: url("../../public/bg2.svg");
  }
  .list {

    //border: 1px solid red;

    position: absolute;
    top: 130px;
    //z-index: 100;
    width: 420px;
    padding: 0 3px;
    //position: absolute;
    //margin-top: 130px;
    color: white;
    // background-color: red;
    overflow: hidden;

    div:nth-child(2n) {
      background-image: url("../assets/icon2.svg");
      // opacity: 0.3;
    }
    div:nth-child(2n + 1) {
      background-image: url("../assets/icon3.svg");
      // opacity: 0.3;
    }
    // width: 100%;
    .item {
      width: 100%;
      height: 50px;
      display: flex;
      opacity: 1;
      font-size: 16px;
      text-align: center;

      .item1 {
        width: 24px;
        // height: 50px;
        height: 100%;
        opacity: 1;
      }
      .item2 {
        flex: 3;
      }
      .item3 {
        flex: 8;
      }
      .item4 {
        flex: 5;
      }
      span {
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
  }
  .right {
    top: 50px;
  }
}
</style>
