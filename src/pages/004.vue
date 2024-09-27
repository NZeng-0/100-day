<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="circle">
        <div class="circle1" />
        <div class="circle2" />
        <div class="circle3" />
      </div>
    </div>
  </div>
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
  border-radius: 3px;
  background: #e56262;
  box-shadow: 1px 2px 13px 0 rgba(0, 0, 0, 0.3);
  color: white;
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.circle {
  position: relative;
  width: 120px;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 2s ease-in;
}

.circle1 {
  position: absolute;
  z-index: 40;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background: white;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
  animation-fill-mode: both;
  animation: jump-jump-1 2s cubic-bezier(0.21, 0.98, 0.6, 0.99) infinite alternate;
}

.circle2 {
  position: absolute;
  z-index: 20;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: white;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
  animation-fill-mode: both;
  animation: jump-jump-2 2s cubic-bezier(0.21, 0.98, 0.6, 0.99) infinite alternate;
}

.circle3 {
  position: absolute;
  z-index: 10;
  width: 90px;
  height: 90px;
  border-radius: 50%;
  background: white;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
  animation-fill-mode: both;
  animation: jump-jump-3 2s cubic-bezier(0.21, 0.98, 0.6, 0.99) infinite alternate;
}

@keyframes jump-jump-1 {
  0%,
  70% {
    box-shadow: 2px 2px 3px 2px rgba(0, 0, 0, 0.2);
    transform: scale(0);
  }
  100% {
    box-shadow: 10px 10px 15px 0 rgba(0, 0, 0, 0.3);
    transform: scale(1);
  }
}

@keyframes jump-jump-2 {
  0%,
  40% {
    box-shadow: 2px 2px 3px 2px rgba(0, 0, 0, 0.2);
    transform: scale(0);
  }
  100% {
    box-shadow: 10px 10px 15px 0 rgba(0, 0, 0, 0.3);
    transform: scale(1);
  }
}

@keyframes jump-jump-3 {
  0%,
  10% {
    box-shadow: 2px 2px 3px 2px rgba(0, 0, 0, 0.2);
    transform: scale(0);
  }
  100% {
    box-shadow: 10px 10px 15px 0 rgba(0, 0, 0, 0.3);
    transform: scale(1);
  }
}
</style>
