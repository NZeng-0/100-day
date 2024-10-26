<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="headline">
        <div class="small">
          your daily
        </div>
        progress
      </div>
      <div class="circle-big">
        <div class="text">
          2758
          <div class="small">
            kcal
          </div>
        </div>
        <svg>
          <circle class="bg" cx="57" cy="57" r="52" />
          <circle class="progress" cx="57" cy="57" r="52" />
        </svg>
      </div>
      <div class="circles-small">
        <div class="circle-small">
          <div class="text">
            8563
            <div class="small">
              steps
            </div>
          </div>
          <svg>
            <circle class="bg" cx="40" cy="40" r="37" />
            <circle class="progress one" cx="40" cy="40" r="37" />
          </svg>
        </div>
        <div class="circle-small">
          <div class="text">
            6,2
            <div class="small">
              km
            </div>
          </div>
          <svg>
            <circle class="bg" cx="40" cy="40" r="37" />
            <circle class="progress two" cx="40" cy="40" r="37" />
          </svg>
        </div>
      </div>
    </div>
  </div>
  <TheCd to="021" class="op-5" :bt="35" />
  <TheCd to="023" :bt="10" />
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
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  background: #28404e;
  background: linear-gradient(to bottom, #28404e 0%, #1c2e38 100%);
  color: #fff;
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

.headline {
  font-weight: 600;
  font-size: 24px;
  text-transform: uppercase;
  text-align: center;
  line-height: 22px;

  .small {
    font-weight: 300;
    font-size: 16px;
  }
}

.circle-big {
  position: relative;
  width: 114px;
  height: 114px;
  margin: 30px auto 25px auto;

  svg {
    width: 114px;
    height: 114px;
  }

  .bg {
    fill: none;
    stroke-width: 10px;
    stroke: #1b2a33;
  }

  .progress {
    fill: none;
    stroke-width: 10px;
    stroke: #27e1ae;
    stroke-linecap: round;
    stroke-dasharray: 232.36;
    stroke-dashoffset: 60;
    transform: rotate(-90deg);
    transform-origin: 50% 50%;
    animation: big 1.5s ease-out;
  }

  .text {
    position: absolute;
    width: 100%;
    top: 37px;
    font-size: 24px;
    text-align: center;
    font-weight: 400;
    line-height: 22px;

    .small {
      font-size: 14px;
      color: #648192;
    }
  }
}

.circles-small {
  margin: 0 auto;
  width: 400px;
  height: 80px;
  text-align: center;
}

.circle-small {
  display: inline-block;
  position: relative;
  width: 80px;
  height: 80px;
  margin: 0 20px;

  svg {
    width: 80px;
    height: 80px;
  }

  .bg {
    fill: none;
    stroke-width: 6px;
    stroke: #1b2a33;
  }

  .progress {
    fill: none;
    stroke-width: 6px;
    stroke: #5ce1ec;
    stroke-linecap: round;
    stroke-dasharray: 326.56;
    transform: rotate(-90deg);
    transform-origin: 50% 50%;

    &.one {
      stroke-dashoffset: 80;
      animation: one 1.5s ease-out;
    }

    &.two {
      stroke-dashoffset: 140;
      animation: two 1.5s ease-out;
    }
  }

  .text {
    position: absolute;
    width: 100%;
    top: 26px;
    font-size: 17px;
    text-align: center;
    font-weight: 400;
    line-height: 16px;

    .small {
      font-size: 12px;
      color: #648192;
    }
  }
}

@keyframes big {
  from {
    stroke-dashoffset: 326.56;
  }
  to {
    stroke-dashoffset: 60;
  }
}

@keyframes one {
  from {
    stroke-dashoffset: 232.36;
  }
  to {
    stroke-dashoffset: 80;
  }
}

@keyframes two {
  from {
    stroke-dashoffset: 232.36;
  }
  to {
    stroke-dashoffset: 140;
  }
}
</style>
