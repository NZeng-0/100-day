<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div v-for="(i, key) in 15" :key :class="`point-set-${i}`">
        <div class="point-1" />
        <div class="point-2" />
        <div class="point-3" />
        <div class="point-4" />
      </div>

      <div class="ring">
        <div class="mask-1">
          <div class="spin" />
        </div>
        <div class="mask-2">
          <div class="spin" />
        </div>
      </div>
      <svg class="spinner" viewBox="0 0 202 202" xlmns="https://www.w3.org/2000/svg">
        <circle cx="101" cy="101" r="99.5" />
      </svg>
      <div class="date">
        Mon 15 Jan 2015
      </div>
      <div class="time">
        11:42
      </div>
      <div class="beat">
        <span class="fa fa-heart" />
        81
      </div>
      <div class="energy">
        1248 kcal
      </div>
    </div>
  </div>

  <TheCd to="009" class="op-5" :bt="35" />
  <TheCd to="011" :bt="10" />
</template>

<style scoped lang="scss">
$speed: 5s; // 60s for realtime

.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  background: #4c4c4c;
  color: #fff;
  font-size: 12px;
  line-height: 100%;
  text-transform: uppercase;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
}

.center {
  position: absolute;
  width: 212px;
  height: 212px;
  top: 87px;
  left: 87px;
  background: #242424;
  border: 7px solid #3a3a3a;
  border-radius: 50%;
  text-align: center;
}

@for $i from 1 through 15 {
  .point-set-#{$i} {
    position: absolute;
    height: 188px;
    width: 188px;
    top: 12px;
    left: 12px;
    transform: rotate((($i - 1) * 6) + deg);

    .point-1 {
      position: absolute;
      width: 2px;
      height: 2px;
      top: 0;
      left: 93px;
      background: #d3d3d3;
      border-radius: 50%;
    }

    .point-2 {
      @extend .point-1;
      top: 93px;
      left: auto;
      right: 0;
    }

    .point-3 {
      @extend .point-1;
      top: auto;
      bottom: 0;
    }

    .point-4 {
      @extend .point-1;
      top: 93px;
      left: 0;
    }
  }
}

.spinner {
  position: absolute;
  width: 202px;
  height: 202px;
  border-radius: 50%;
  top: 5px;
  left: 5px;

  circle {
    stroke: #f85b5b;
    stroke-width: 3;
    fill: none;
    stroke-dasharray: 625;
    animation: spinner $speed ease-in-out infinite;
    transform-origin: center center;
    transform: rotate(-90deg);
  }
}

.date {
  position: absolute;
  top: 68px;
  width: 100%;
}

.time {
  position: absolute;
  top: 80px;
  width: 100%;
  font-weight: 700;
  font-size: 40px;
  line-height: 100%;
  margin: 4px 0;
}

.beat {
  position: absolute;
  top: 129px;
  left: 57px;

  span {
    color: #f85b5b;
    font-size: 10px;
    float: left;
    margin-top: 1px;
    margin-right: 4px;
    animation: beat 0.9s ease-in-out infinite;
  }
}

.energy {
  position: absolute;
  top: 129px;
  right: 55px;
}

@keyframes spinner {
  from {
    stroke-dashoffset: 625;
    transform: rotate(-90deg) scaleY(1);
  }
  50% {
    stroke-dashoffset: 0;
    transform: rotate(-90deg) scaleY(1);
  }
  50.001% {
    transform: rotate(-90deg) scaleY(-1);
  }

  to {
    stroke-dashoffset: 625;
    transform: rotate(-90deg) scaleY(-1);
  }
}

@keyframes beat {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(1.2);
  }
}
</style>
