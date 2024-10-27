<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="dots">
      <div v-for="e in 20" :key="e" :class="`dot dot-${e}`" />
    </div>
  </div>
  <TheCd to="029" class="op-5" :bt="35" />
  <TheCd to="032" :bt="10" />
</template>

<style lang="scss" scoped>
$duration: 60;
$numberOfDots: 20;
$oscillations: 40;

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
  background: #4c4ba2;
}

.dots {
  padding-top: 28px;
  padding-left: 194px;

  .dot {
    width: 12px;
    height: 12px;
    background: #fff;
    border-radius: 50%;
    margin: 5px 0;
  }
}

@for $i from 1 through $numberOfDots {
  $time: $duration / ($oscillations + $numberOfDots - $i);

  .dot-#{$i} {
    animation: dot ($time * 1000) + ms ease-in-out infinite;
  }

  // .dot-#{$i} {
  //   animation: dot-#{$i} ($time * 1000) + ms ease-in-out infinite;
  // }

  @keyframes dot-#{$i} {
    0%,
    100% {
      transform: translate3d(($i * 8) + px, 0, 0);
    }

    50% {
      transform: translate3d(($i * -8) + px, 0, 0);
    }
  }
}

@keyframes dot {
  0%,
  100% {
    transform: translate3d(50px, 0, 0);
  }

  50% {
    transform: translate3d(-50px, 0, 0);
  }
}
</style>
