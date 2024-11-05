<script setup lang="ts"></script>

<template>
  <div class="frame">
    <div class="circle" />
    <div class="center">
      <svg width="400px" height="65px" viewBox="0 0 400 65" class="line">
        <path
          d="M0,4.67941475 C0,4.67941475 42.5049504,21.0558251 95.0896109,21.0558243 C147.674271,21.0558235 149.896403,2 196.011077,2 C242.125751,2 242.386923,58.3217419 200.000004,58.3217392 C157.613085,58.3217365 163.18433,13.5133498 212.755329,13.5133498 C262.326328,13.5133498 284.162205,38.9236796 335.140774,38.9236794 C386.119343,38.9236791 399.999996,30.1608696 399.999996,30.1608696"
        />
      </svg>
    </div>
  </div>
</template>

<style lang="scss" scoped>
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
  background: #16a085;
  font-size: 0;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.line {
  fill: none;
  stroke: #fff;
  stroke-width: 3px;
  stroke-linecap: round;
  animation: line 2.5s linear infinite;
}

.circle {
  position: absolute;
  width: 30px;
  height: 30px;
  top: 185px;
  left: 185px;
  border-radius: 50%;
  border: 4px solid white;
  animation: circle 2.5s ease-out infinite both;
}

@keyframes line {
  from {
    stroke-dasharray: 50 660;
    stroke-dashoffset: 780;
  }
  to {
    stroke-dasharray: 50 660;
    stroke-dashoffset: 70;
  }
}

@keyframes circle {
  0%,
  50% {
    opacity: 1;
    transform: scale(0);
  }
  70%,
  100% {
    opacity: 0;
    transform: scale(0.8);
  }
}
</style>
