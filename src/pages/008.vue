<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="ball" />
      <div v-for="(i, key) in 8" :key :class="`absorb_${i}`" />
      <div v-for="(i, key) in 10" :key :class="`sparkle_${i}`" />
    </div>
  </div>

  <TheCd to="007" class="op-5" :bt="35" />
  <TheCd to="009" :bt="10" />
</template>

<style scoped lang="scss">
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  background: #000;
  filter: contrast(25);
}

.center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.ball {
  position: relative;
  width: 90px;
  height: 90px;
  background: #fff;
  border-radius: 50%;
  filter: blur(15px);
}

@for $i from 1 through 8 {
  .absorb_#{$i} {
    position: absolute;
    top: 20px;
    left: 20px;
    width: 50px;
    height: 50px;
    transform: rotate(random(300) + deg);

    &:after {
      position: absolute;
      display: block;
      content: ' ';
      width: 50px;
      height: 50px;
      background: white;
      border-radius: 50%;
      transform-origin: (40 - $i * 3) + px (40 - $i * 3) + px;
      animation: rotate (2.5 + $i / 5) + s ease-in-out ($i / 5) + s infinite;
      filter: blur(5px);
    }
  }
}

@for $i from 1 through 10 {
  .sparkle_#{$i} {
    position: absolute;
    top: 38px;
    left: 38px;
    width: (7 + $i) + px;
    height: (7 + $i) + px;
    transform: rotate((random(300)) + deg);

    &:after {
      position: absolute;
      display: block;
      content: '';
      width: (7 + $i) + px;
      height: (7 + $i) + px;
      background: #fff;
      border-radius: 50%;
      transform-origin: (60 - $i * 2) + px (60 - $i * 2) + px;
      animation: rotate (3.5 + $i / 5) + s ease-in-out ($i / 5) + s infinite;
      filter: blur(3px);
    }
  }
}

@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
