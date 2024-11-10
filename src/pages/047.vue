<script setup lang="ts">
const arr = [
  130,
  131,
  149,
  150,
  151,
  152,
  168,
  169,
  170,
  171,
  172,
  173,
  187,
  188,
  190,
  191,
  193,
  194,
  207,
  208,
  209,
  210,
  211,
  212,
  213,
  214,
  229,
  232,
  248,
  250,
  251,
  253,
  267,
  269,
  272,
  274,
]

function isInit(key: number) {
  return arr.includes(key)
}
</script>

<template>
  <div class="frame">
    <div v-for="i in 400" :key="i" class="pixel">
      <input v-if="isInit(i)" :id="`pixel-${i}`" type="checkbox" checked>

      <template v-else>
        <input :id="`pixel-${i}`" type="checkbox">
      </template>
      <label :for="`pixel-${i}`" class="tab" />
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
  background: #de4738;
  color: #fff;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.pixel {
  float: left;

  input {
    display: none;
  }

  label {
    box-sizing: border-box;
    display: block;
    width: 20px;
    height: 20px;
    border: 1px solid #e24e3f;
    cursor: pointer;

    &:hover {
      background: #ec5142;
      border-color: #e24e3f;
    }
  }

  input:checked ~ label {
    background: #fff;
    border: #fff;
  }
}
</style>
