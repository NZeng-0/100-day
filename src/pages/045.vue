<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="button" onclick="void(0);">
        <span>Hover me</span>
        <svg width="180px" height="60px" viewBox="0 0 180 60" class="border">
          <polyline points="179,1 179,59 1,59 1,1 179,1" class="bg-line" />
          <polyline points="179,1 179,59 1,59 1,1 179,1" class="hl-line" />
        </svg>
        <div />
      </div>
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
  background: #5ca4ea;
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

.button {
  position: relative;
  cursor: pointer;

  span {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    text-align: center;
    line-height: 58px;
    text-transform: uppercase;
    font-size: 18px;
    letter-spacing: 1px;
    font-weight: 300;
  }

  .border {
    fill: none;
    stroke-width: 1;
  }

  .bg-line {
    fill: #5ca4ea;
    stroke: #91c9ff;
    transition: all 0.8s ease-in-out;
  }

  .hl-line {
    stroke: #fff;
    stroke-dasharray: 40 480;
    stroke-dashoffset: 40;
    transition: all 0.8s ease-in-out;
  }
  &:hover {
    .bg-line {
      fill: #4f95da;
    }

    .hl-line {
      stroke-dashoffset: -480;
    }
  }
}
</style>
