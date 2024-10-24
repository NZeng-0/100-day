<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="moon">
      <div v-for="(i, key) in 10" :key :class="`crater-${i} crater`" />
    </div>

    <div class="hill-bg-1 hill" />
    <div class="hill hill-bg-2" />
    <div class="hill hill-fg-1" />
    <div class="hill hill-fg-2" />
    <div class="hill hill-fg-3" />

    <div class="front">
      <div class="temperature">
        12°
      </div>
      <div class="info">
        Wind: E 7 km/h <br> Humidity: 87%
      </div>
      <table class="preview">
        <tr>
          <td>Tue</td>
          <td>21° / 9°</td>
        </tr>
        <tr>
          <td>Wed</td>
          <td>23° / 10°</td>
        </tr>
      </table>
    </div>

    <div v-for="(i, key) in 10" :key :class="`drop-big-${i}`" />

    <div v-for="(i, key) in 10" :key :class="`drop-medium-${i}`" />

    <div v-for="(i, key) in 10" :key :class="`drop-small-${i}`" />
  </div>

  <TheCd to="008" class="op-5" :bt="35" />
  <TheCd to="010" :bt="10" />
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
  box-shadow: 1px 2px 13px 0 rgba(0, 0, 0, 0.3);
  background: #1a2238;
  color: #394568;
  font-family: 'Open Sans', Helvetica, sans-serif;
  font-weight: 300;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
}

.moon {
  position: absolute;
  width: 67px;
  height: 67px;
  top: 45px;
  left: 55px;
  border-radius: 50px;
  background: #f6edbd;
  overflow: hidden;
  box-shadow: 0 0 10px 0 #f6edbd;
  animation: rise 1s ease-out;

  .crater {
    position: absolute;
    width: 11px;
    height: 11px;
    top: 9px;
    left: 28px;
    border-radius: 10px;
    background: #ece1a8;
  }

  .crater-2 {
    top: 12px;
    left: 0;
  }

  .crater-3 {
    top: 56px;
    left: 10px;
  }

  .crater-4 {
    width: 6px;
    height: 6px;
    top: 37px;
    left: 49px;
  }

  .crater-5 {
    top: 24px;
    left: 61px;
  }

  .crater-6 {
    top: 55px;
    left: 33px;
  }

  .crater-7 {
    top: 17px;
    left: 46px;
  }

  .crater-8 {
    top: 28px;
    left: 27px;
  }

  .crater-9 {
    top: 39px;
    left: 17px;
  }

  .crater-10 {
    width: 4px;
    height: 4px;
    top: 25px;
    left: 15px;
  }

  .crater-11 {
    top: 37px;
    left: 37px;
  }
}

.hill {
  position: absolute;
  z-index: 2;
  width: 337px;
  height: 281px;
  top: 201px;
  left: -57px;
  background: #26314f;
  border-radius: 50%;
}

.hill-bg-2 {
  top: 197px;
  left: 177px;
}

.hill-fg-1 {
  background: #303c5d;
  top: 248px;
  left: -137px;
}

.hill-fg-2 {
  top: 221px;
  left: 63px;
  background: #303c5d;
}

.hill-fg-3 {
  top: 248px;
  left: 292px;
  background: #303c5d;
}

.front {
  position: absolute;
  z-index: 10;
  width: 400px;
  height: 90px;
  left: 0;
  bottom: 0;
  background: #fff;

  .temperature {
    float: left;
    margin-left: 20px;
    font-size: 45px;
    line-height: 90px;
  }

  .info {
    float: left;
    margin: 25px 0 0 15px;
    font-size: 15px;
    line-height: 20px;
  }

  .preview {
    float: right;
    font-weight: 400;
    text-align: right;
    font-size: 15px;
    line-height: 20px;
    margin: 25px 20px 0 0;

    td {
      padding: 0 3px;
      text-transform: uppercase;

      &:first-child {
        font-weight: 300;
      }
    }
  }
}

@for $i from 1 through 10 {
  .drop-big-#{$i} {
    position: absolute;
    z-index: 20;
    left: (-20 + 38 * $i) + px;
    bottom: 90px;
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: var(--drop-color);
    animation: drop (0.7 + random(2) / 10) + s linear (random(50) / 25) + s infinite;
    animation-fill-mode: both;
    transform-origin: 50% 100%;

    &:before {
      position: absolute;
      content: '';
      display: block;
      top: -2px;
      left: 1px;
      width: 6px;
      height: 6px;
      background: var(--drop-color);
      border-radius: 3px;
    }

    &:after {
      position: absolute;
      content: '';
      display: block;
      top: -5px;
      left: 2px;
      width: 4px;
      height: 10px;
      background: var(--drop-color);
      border-radius: 50%;
    }
  }

  .drop-medium-#{$i} {
    @extend .drop-big-1;
    left: (-20 + 38 * $i) + px;
    opacity: 0.6;
    width: 6px;
    height: 6px;
    animation: drop (1.3 + random(2) / 10) + s linear (random(50) / 25) + s infinite;
    animation-fill-mode: both;

    &:before {
      top: -2px;
      left: 1px;
      width: 4px;
      height: 4px;
    }

    &:after {
      top: -4px;
      left: 2px;
      width: 2px;
      height: 6px;
    }
  }

  .drop-small-#{$i} {
    @extend .drop-big-1;
    left: (-20 + 38 * $i) + px;
    opacity: 0.3;
    width: 4px;
    height: 4px;
    animation: drop (1.9 + random(2) / 10) + s linear (random(50) / 25) + s infinite;
    animation-fill-mode: both;

    &:before {
      top: -3px;
      left: 1px;
      width: 2px;
      height: 2px;
    }

    &:after {
      top: -3px;
      left: 1px;
      width: 2px;
      height: 4px;
    }
  }
}

@keyframes drop {
  0% {
    transform: translate3d(40px, -320px, 0) scaleX(1) scaleY(1) rotate(17deg);
  }
  85% {
    transform: translate3d(0, 0, 0) scaleX(1) scaleY(1) rotate(17deg);
  }
  100% {
    transform: translate3d(0, 0, 0) scaleX(3) scaleY(0) rotate(0deg);
  }
}

@keyframes rise {
  from {
    transform: translate(-20px, 200px);
  }
  to {
    transform: translate(0, 0px);
  }
}
</style>
