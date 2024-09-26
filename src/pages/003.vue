<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="circle">
        <div class="sky" />
        <div class="sun" />
        <div class="side_left" />
        <div class="side_right" />
        <div class="shadow" />
        <div class="ground" />
      </div>
    </div>
  </div>
</template>

<style>
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  box-shadow: 1px 2px 13px 0 rgba(0, 0, 0, 0.3);
  background: #272c34;
  color: #fff;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.circle {
  width: 180px;
  height: 180px;
  clip-path: circle(90px at 50% 50%);
  overflow: hidden;
  border-radius: 50%;

  .sky {
    width: 100%;
    height: 124px;
    background: #7ddffc;
    animation: sky 4s cubic-bezier(0.4, 0, 0.49, 1) infinite;
  }

  .sun {
    width: 34px;
    height: 34px;
    border-radius: 50%;
    background: #ffef00;
    position: absolute;
    top: 7px;
    left: 73px;
    transform-origin: 50% 400%;
    animation: sun 4s cubic-bezier(0.4, 0, 0.49, 1) infinite;
  }

  .side_left {
    width: 116px;
    height: 57px;
    background: #f4f4f4;
    clip-path: polygon(0% 100%, 100% 100%, 50% 0%);
    position: absolute;
    top: 67px;
    left: 35px;
    animation: side 4s cubic-bezier(0.4, 0, 0.49, 1) infinite;
  }

  .side_right {
    width: 58px;
    height: 57px;
    background: #dddddd;
    clip-path: polygon(30% 100%, 100% 100%, 0% 0%);
    position: absolute;
    top: 67px;
    left: 93px;
    animation: side 4s cubic-bezier(0.4, 0, 0.49, 1) infinite reverse;
  }

  .shadow {
    width: 360px;
    height: 36px;
    background: rgba(0, 0, 0, 0.2);
    clip-path: polygon(115px 0%, 231px 0%, 80% 100%);
    position: absolute;
    top: 124px;
    left: -80px;
    transform-origin: 50% 0;
    animation: shadow 4s cubic-bezier(0.4, 0, 0.49, 1) infinite;
  }

  .ground {
    width: 100%;
    height: 56px;
    background: #f0de75;
    animation: ground 4s cubic-bezier(0.4, 0, 0.49, 1) infinite;
  }
}

@keyframes sky {
  0% {
    background: #272c34;
  }

  30% {
    background: #7ddffc;
  }

  70% {
    background: #7ddffc;
  }

  100% {
    background: #272c34;
  }
}

@keyframes sun {
  0% {
    background: #e63535;
    rotate: -70deg;
  }

  30% {
    background: #ffef00;
    rotate: -28deg;
  }

  70% {
    background: #ffef00;
  }

  100% {
    background: #e63535;
    rotate: 70deg;
  }
}

@keyframes side {
  0% {
    background: #272c34;
  }

  30% {
    background: #f4f4f4;
  }

  70% {
    background: #dddada;
  }

  100% {
    background: #272c34;
  }
}

@keyframes shadow {
  0% {
    transform: scaleY(0);
    clip-path: polygon(115px 0%, 231px 0%, 100% 100%);
  }

  30% {
    transform: scaleY(1);
    clip-path: polygon(115px 0%, 231px 0%, 80% 100%);
  }

  55% {
    transform: scaleY(1);
  }

  70% {
    transform: scaleY(1);
  }

  100% {
    transform: scaleY(1);
    clip-path: polygon(115px 0%, 231px 0%, 0% 100%);
  }
}

@keyframes ground {
  0% {
    background: #272c34;
  }

  30% {
    background: #f0de75;
  }

  70% {
    background: #f0de75;
  }

  100% {
    background: #272c34;
  }
}
</style>
