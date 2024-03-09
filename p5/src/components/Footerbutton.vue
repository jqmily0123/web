<template>
  <div class="footer_button">
    <div class="icon">
      <slot></slot>
    </div>
    <div class="icon_dec">
      {{ iconDec }}
    </div>
  </div>
</template>
<script setup>
const props = defineProps({
  iconDec: {
    type: String,
  },
});
</script>
<style scoped lang="less">
.footer_button {
  width: 70px;
  height: 120px;
  .icon_dec {
    height: 38px;
    line-height: 38px;
    text-align: center;
    font-size: 24px;
    color: #fff;
    text-indent: 0.78px;
  }
}
</style>
