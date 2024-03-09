<template>
  <div class="p">
    <div class="layout">
      <layout></layout>
    </div>
  </div>
</template>
<script>
import Layout from "./view/Layout.vue";
export default {
  components: { Layout },
  setup() {},
};
</script>
<style lang="less">
@import url("./assets/commonStyle.less");
html,
body,
#app,
.p1 {
  height: 100%;
  width: 100%;
  background-color: @backgroundColor;
  z-index: -1;
  display: flex;
  justify-content: center;
}
</style>
