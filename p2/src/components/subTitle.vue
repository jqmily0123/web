<template>
  <div>
    <div class="sub-title">
      <div class="s-title">
        <div class="text">{{ text }}</div>
        <div class="s-svg">
          <svg width="49" height="49" viewBox="0 0 49 49" fill="none">
            <g opacity="1" transform="translate(0 5)  rotate(0)">
              <path
                id="矩形"
                fill-rule="evenodd"
                style="fill: #66ffff"
                opacity="1"
                d="M48.9744 7.94183e-16L42.8944 -4.63L36.0044 -4.63L42.0744 3.7168e-16L48.9744 7.94183e-16Z"
              ></path>
              <path
                id="矩形"
                fill-rule="evenodd"
                style="fill: #66ffff"
                opacity="1"
                d="M36.7176 7.94183e-16L30.6376 -4.63L23.7476 -4.63L29.8176 3.7168e-16L36.7176 7.94183e-16Z"
              ></path>
              <path
                id="矩形"
                fill-rule="evenodd"
                style="fill: #66ffff"
                opacity="1"
                d="M25.2268 7.94183e-16L19.1468 -4.63L12.2568 -4.63L18.3268 3.7168e-16L25.2268 7.94183e-16Z"
              ></path>
              <path
                id="矩形"
                fill-rule="evenodd"
                style="fill: #66ffff"
                opacity="1"
                d="M12.97 7.94183e-16L6.89 -4.63L2.83506e-16 -4.63L6.07 3.7168e-16L12.97 7.94183e-16Z"
              ></path>
            </g>
          </svg>
        </div>
      </div>
      <div class="deadline">截止时间至{{ currentTime }}</div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  currentTime: {
    type: String,
  },
  text: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.sub-title {
  height: 30px;
  display: flex;
  justify-content: space-between;
  padding: 0 10px;
  margin-bottom: 20px;
  .s-title {
    .text {
      font-size: 16px;
      font-weight: 600;
      color: white;
      margin-bottom: 2px;
    }
  }
  .deadline {
    color: white;
    opacity: 0.6;
    font-size: 10px;
    line-height: 30px;
  }
}
</style>
