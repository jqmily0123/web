<template>
  <div>
    <div class="title">
      <div class="text">{{ title }}</div>
      <div class="t-svg">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="120"
          height="9.923675537109375"
          viewBox="0 0 120 9.923675537109375"
          fill="none"
        >
          <path
            id="形状结合"
            fill-rule="evenodd"
            fill="url(#linear_44)"
            opacity="1"
            d="M3.87,9.92h-3.87v-9.92h3.87zM11.1281,9.92h-3.87v-9.92h3.87zM18.3861,9.92h-3.87v-9.92h3.87zM25.6442,9.92h-3.87v-9.92h3.87zM32.9022,9.92h-3.87v-9.92h3.87zM40.1603,9.92h-3.87v-9.92h3.87zM47.4183,9.92h-3.87v-9.92h3.87zM54.6764,9.92h-3.87v-9.92h3.87zM61.9345,9.92h-3.87v-9.92h3.87zM69.1925,9.92h-3.87v-9.92h3.87zM76.4506,9.92h-3.87v-9.92h3.87zM83.7086,9.92h-3.87v-9.92h3.87zM90.9667,9.92h-3.87v-9.92h3.87zM98.2247,9.92h-3.87v-9.92h3.87zM105.483,9.92h-3.87v-9.92h3.87zM112.741,9.92h-3.87v-9.92h3.87zM119.999,9.92h-3.87v-9.92h3.87z"
          ></path>
          <defs>
            <linearGradient
              id="linear_44"
              x1="0%"
              y1="50.00000000000071%"
              x2="100%"
              y2="50.000000000000355%"
              gradientUnits="objectBoundingBox"
            >
              <stop offset="0" stop-color="#00ADBD" stop-opacity="1" />
              <stop
                offset="0.5413888841303635"
                stop-color="#00FFC7"
                stop-opacity="1"
              />
              <stop offset="1" stop-color="#00B6C7" stop-opacity="1" />
            </linearGradient>
          </defs>
        </svg>
      </div>
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
.title {
  width: 100%;
  font-size: 22px;
  font-weight: 600;
  color: white;
  text-align: center;

  //   margin: 20px 0;
  margin-top: 40px;
  //   background-color: red;
}
</style>
