<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="number">
        <div class="one-one" />
        <div class="one-two" />
        <div class="zero-one" />
        <div class="zero-two" />
      </div>
      <span class="big">Days</span>
      <span class="small">CSS Challenge</span>
    </div>
  </div>
  <TheCd to="002" :bt="10" />
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
  color: #fff;
  background: #43389f;
  background: linear-gradient(to top right, #43389f 0%, #4ec6ca 100%);
  font-family: 'Courier New', 'Courier', sans-serif;
  -webkit-font-smoothing: antialiased;
}

.center {
  position: absolute;
  top: 50.8%;
  left: 50.5%;
  transform: translate(-50%, -50%);
}

.number {
  position: relative;
  width: 200px;
  height: 100px;
}

.one-one {
  position: absolute;
  z-index: 1;
  top: 0;
  left: -16px;
  width: 20px;
  height: 40px;
  background: #fff;
  transform: rotate(50deg);
  border-radius: 3px;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
}

.one-two {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 10;
  width: 24px;
  height: 100px;
  background: #fff;
  border-radius: 3px;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
}

.zero-one,
.zero-two {
  position: absolute;
  top: 0;
  left: 17px;
  z-index: 8;
  width: 100px;
  height: 100px;
  box-sizing: border-box;
  border-radius: 50%;
  border: 24px solid #fff;
  box-shadow: 0 0 13px 0 rgba(0, 0, 0, 0.2);
}

.zero-two {
  z-index: 6;
  left: 100px;
}

.big {
  position: relative;
  z-index: 20;
  display: block;
  font-size: 82px;
  line-height: 60px;
  text-transform: uppercase;
  font-weight: 700;
  margin-top: 6px;
}

.small {
  position: relative;
  display: block;
  z-index: 20;
  font-size: 23px;
  line-height: 20px;
  text-transform: uppercase;
  font-weight: 700;
  letter-spacing: 0.04em;
}
</style>
