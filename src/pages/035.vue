<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <svg width="100px" height="100px" viewBox="0 0 100 100">
        <circle class="bg" cx="50" cy="50" r="46" />
        <circle class="loader" cx="50" cy="50" r="46" />
      </svg>
    </div>
  </div>
</template>

<style scoped lang="scss">
$length: 288;

.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 2px;
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  background: #1bbe9e;
  color: #fff;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.bg {
  fill: none;
  stroke: #12836d;
  stroke-width: 4;
}

.loader {
  fill: none;
  stroke: #fff;
  stroke-width: 4;
  stroke-linecap: round;
  stroke-dasharray: $length;
  animation:
    line 4s linear infinite,
    spin 3s linear infinite;
  transform-origin: 50% 50%;
}

@keyframes line {
  0% {
    stroke-dashoffset: ($length * 4);
  }
  100% {
    stroke-dashoffset: ($length * 2);
  }
}

@keyframes spin {
  0% {
    transform: rotate(-90deg) translate3d(0, 0, 0);
  }
  100% {
    transform: rotate(270deg) translate3d(0, 0, 0);
  }
}
</style>
