<script setup lang="ts">
defineProps<{
  to: string
  bt: number
}>()
</script>

<template>
  <RouterLink :to class="custom" :style="{ bottom: `${bt}px` }">
    cd {{ to }}
  </RouterLink>
</template>

<style scoped>
.custom {
  color: rgb(163 163 163 / 1);
  text-decoration: none;
  font-size: 1rem;
  font-weight: 400;
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  position: absolute;
  left: 10px;
  transition: 0.3s all ease-in-out;
}
</style>
