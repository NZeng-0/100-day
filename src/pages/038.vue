<script setup lang="ts">
const active = ref(false)
</script>

<template>
  <div class="frame" @click="active = !active">
    <div class="logo white" :class="{ big: active, normal: !active }">
      <svg width="70px" height="80px" viewBox="0 0 70 80">
        <path d="M-4.67739102e-15,21.1739614 L-5.32907052e-15,20 L34.6410162,0 L69.2820323,20 L69.2820323,21.1739614 C65.1281093,26.3215737 62.6410162,32.870341 62.6410162,40 C62.6410162,47.129659 65.1281093,53.6784263 69.2820323,58.8260386 L69.2820323,60 L34.6410162,80 L1.687539e-14,60 L1.62237105e-14,58.8260386 C4.15392303,53.6784263 6.64101615,47.129659 6.64101615,40 C6.64101615,32.870341 4.15392303,26.3215737 2.88213897e-13,21.1739614 Z" />
      </svg>
    </div>
    <div class="logo purple small" :class="{ 'small normal': active }">
      <svg width="70px" height="80px" viewBox="0 0 70 80">
        <path d="M-4.67739102e-15,21.1739614 L-5.32907052e-15,20 L34.6410162,0 L69.2820323,20 L69.2820323,21.1739614 C65.1281093,26.3215737 62.6410162,32.870341 62.6410162,40 C62.6410162,47.129659 65.1281093,53.6784263 69.2820323,58.8260386 L69.2820323,60 L34.6410162,80 L1.687539e-14,60 L1.62237105e-14,58.8260386 C4.15392303,53.6784263 6.64101615,47.129659 6.64101615,40 C6.64101615,32.870341 4.15392303,26.3215737 2.88213897e-13,21.1739614 Z" />
      </svg>
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
  background: #9b59b6;
  color: #fff;
  cursor: pointer;
}

.logo {
  position: absolute;
  top: 160px;
  left: 165px;

  &.white svg {
    fill: #fff;
  }

  &.purple svg {
    fill: #9b59b6;
  }

  &.small {
    transform: scale(0);
    transition: all 0.5s ease-in;
  }

  &.normal {
    transform: scale(1);
    transition: all 0.5s ease-out 0.3s;
  }

  &.big {
    transform: scale(10);
    transition: all 0.5s ease-in;
  }
}
</style>
