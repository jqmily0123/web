<template>
  <div class="subtitle">
    <div class="title">{{ title }}</div>
    <div class="svg">
      <svg
        width="65.117919921875"
        height="20"
        viewBox="0 0 65.117919921875 20"
        fill="none"
      >
        <g opacity="1" transform="translate(0 7)  rotate(0)">
          <path
            id="矩形"
            fill-rule="evenodd"
            style="fill: #66ffff"
            opacity="1"
            d="M65.041 1.03632e-15L56.981 -6.04L47.821 -6.04L55.891 4.85662e-16L65.041 1.03632e-15Z"
          ></path>
          <path
            id="矩形"
            fill-rule="evenodd"
            style="fill: #66ffff"
            opacity="1"
            d="M48.7615 1.03632e-15L40.7015 -6.04L31.5415 -6.04L39.6115 4.85662e-16L48.7615 1.03632e-15Z"
          ></path>
          <path
            id="矩形"
            fill-rule="evenodd"
            style="fill: #66ffff"
            opacity="1"
            d="M33.4995 1.03632e-15L25.4395 -6.04L16.2795 -6.04L24.3495 4.85662e-16L33.4995 1.03632e-15Z"
          ></path>
          <path
            id="矩形"
            fill-rule="evenodd"
            style="fill: #66ffff"
            opacity="1"
            d="M17.22 1.03632e-15L9.16 -6.04L3.76303e-16 -6.04L8.07 4.85662e-16L17.22 1.03632e-15Z"
          ></path>
        </g>
      </svg>
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  title: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.subtitle {
  color: white;
  font-size: 22px;
  //font-weight: 700;
  //font-weight: bolder;
  .svg {
    margin-top: 15px;
  }
}
</style>
