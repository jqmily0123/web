<template>
  <div class="example-circlekuosan">
    <div class="circle-btn"></div>
  </div>
</template>

<script setup></script>
<style scoped lang="less">
.example-circlekuosan {
  display: flex;
  justify-content: center;
  position: relative;
}
.circle-btn {
  width: 24px;
  height: 24px;
  overflow: hidden;
  background-color: yellow;
  opacity: 0;
  border-radius: 100%;
  box-shadow: 0 0 0 0 rgba(236, 169, 69, 0.7);
  cursor: pointer;
  animation: pulsedb 2s infinite;
}

@keyframes pulsedb {
  0% {
    box-shadow: 0 0 0 0 rgba(236, 169, 69, 0.5);
    opacity: 0;
  }
  70% {
    box-shadow: 0 0 0 3px rgba(236, 169, 69, 0.9),
      0 0 0 6px rgba(236, 169, 69, 0.6), 0 0 0 10px rgba(236, 169, 69, 0.3);
    opacity: 1;
  }
  100% {
    box-shadow: 0 0 0 3px rgba(236, 169, 69, 0), 0 0 0 6px rgba(236, 169, 69, 0),
      0 0 0 10px rgba(236, 169, 69, 0);
  }
}
</style>
