<script setup lang="ts">
const num = ref(0)

function foo() {
  num.value++
  if (num.value === 3) {
    num.value = 0
  }
}
</script>

<template>
  <div class="frame">
    <div class="card" :class="num === 0 ? 'active' : 'inactive'">
      <div class="number-bg" />
      <div class="number">
        1
      </div>
      <div class="text">
        <span class="headline">The couch</span>
        <p>If you want to grow, get outside<br> your comfort zone.</p>
      </div>
      <div class="button" @click="foo">
        Ok
      </div>
    </div>
    <div class="card" :class="num === 1 ? 'active' : 'inactive'">
      <div class="number-bg" />
      <div class="number">
        2
      </div>
      <div class="text">
        <span class="headline">Failing is learning</span>
        <p>Pick yourself up, dust yourself off,<br> and start again.</p>
      </div>
      <div class="button" @click="foo">
        Ok
      </div>
    </div>
    <div class="card" :class="num === 2 ? 'active' : 'inactive'">
      <div class="number-bg" />
      <div class="number">
        3
      </div>
      <div class="text">
        <span class="headline">Flowers and rainbows</span>
        <p>Always be yourself,<br> unless you can be a unicorn.</p>
      </div>
      <div class="button" @click="foo">
        Ok
      </div>
    </div>
  </div>
  <TheCd to="025" class="op-5" :bt="35" />
  <TheCd to="027" :bt="10" />
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
  box-shadow: 1px 2px 10px 0px rgba(0, 0, 0, 0.15);
  overflow: hidden;
  background: #c7d6e1;
  color: #fff;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.card {
  position: absolute;
  z-index: 0;
  width: 240px;
  height: 150px;
  top: 125px;
  left: 80px;
  background: #fff;
  box-shadow: 4px 8px 12px 0px rgba(0, 0, 0, 0.1);
  border-radius: 3px;
  overflow: hidden;
  pointer-events: none;
  opacity: 0;
  transform: scale(0.5);

  &.active {
    pointer-events: all;
    z-index: 1;
    animation: fadeIn 0.6s ease-in-out both 0.5s;
  }

  &.inactive {
    z-index: 2;
    animation: fadeOut 0.5s ease-in-out both;
  }

  .number-bg {
    position: absolute;
    width: 60px;
    height: 60px;
    top: -31px;
    right: -31px;
    background: #8391a1;
    transform: rotate(45deg);
  }

  .number {
    position: absolute;
    top: 6px;
    right: 8px;
    font-size: 13px;
    line-height: 13px;
    font-weight: 600;
    color: #fff;
  }

  .text {
    text-align: center;
    padding: 20px 10px;

    .headline {
      display: block;
      font-size: 14px;
      line-height: 22px;
      font-weight: 600;
      color: #616e7d;
      margin-bottom: 8px;
    }

    p {
      font-size: 12px;
      line-height: 17px;
      color: #8391a1;
      margin: 0;
    }
  }

  .button {
    position: absolute;
    width: 100%;
    height: 40px;
    bottom: 0;
    left: 0;
    right: 0;
    background: #3ca7fb;
    cursor: pointer;
    text-align: center;
    text-transform: uppercase;
    line-height: 38px;
    font-size: 13px;
    transition: all 0.3s ease-in-out;

    &:hover {
      background: #2196f3;
    }
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.9);
  }

  to {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes fadeOut {
  from {
    opacity: 1;
    transform: scale(1);
  }

  to {
    opacity: 0;
    transform: scale(1.15);
  }
}
</style>
