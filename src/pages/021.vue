<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <svg class="pacman">
      <circle cx="50" cy="50" r="25" />
    </svg>
    <svg class="eye">
      <circle cx="6" cy="6" r="6" />
    </svg>
    <svg class="dots">
      <polyline points="0,7 240,7" />
    </svg>
  </div>
  <TheCd to="020" class="op-5" :bt="35" />
  <TheCd to="022" :bt="10" />
</template>

<style scoped>
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 2px;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  background: #2c2e2e;
  overflow: hidden;
}

.pacman {
  position: absolute;
  width: 100px;
  height: 100px;
  top: 150px;
  left: 150px;
  fill: none;
  stroke: #f4d146;
  stroke-width: 50px;
  stroke-linecap: butt;
  stroke-dasharray: 157;
  animation: mouth var(--speed) ease-in-out infinite;
}

.eye {
  position: absolute;
  width: 12px;
  height: 12px;
  top: 167px;
  left: 204px;
  fill: #2c2e2e;
  animation: eye var(--speed) ease-in-out infinite;
}

.dots {
  position: absolute;
  height: 14px;
  width: 240px;
  top: 193px;
  left: 180px;
  stroke: #f4d146;
  stroke-width: 14px;
  stroke-dasharray: 0 50px;
  stroke-linecap: round;
  animation: points var(--speed) linear infinite;
  stroke-dashoffset: 14;
}

@keyframes mouth {
  0%,
  100% {
    stroke-dashoffset: 0;
    transform: rotate(0deg) translate3d(0, 0, 0);
  }
  50% {
    stroke-dashoffset: 39.25;
    transform: rotate(45deg);
  }
}

@keyframes eye {
  0%,
  100% {
    transform: translate3d(0, 0, 0);
  }
  50% {
    transform: translate3d(-6px, -3px, 0);
  }
}

@keyframes points {
  0% {
    stroke-dashoffset: 14;
    transform: translate3d(0, 0, 0);
  }
  100% {
    stroke-dashoffset: 64;
  }
}
</style>
