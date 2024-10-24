<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="invisible-men">
      <div class="leg left">
        <div class="shoe" />
      </div>
      <div class="leg right">
        <div class="shoe" />
      </div>
    </div>
    <div class="floor" />
  </div>
  <TheCd to="010" class="op-5" :bt="35" />
  <TheCd to="012" :bt="10" />
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
  border-radius: 3px;
  background: rgb(246, 232, 215);
  box-shadow: 1px 2px 13px 0 rgba(0, 0, 0, 0.3);
  background: radial-gradient(ellipse at center, rgba(246, 232, 215, 1) 0%, rgba(218, 190, 155, 1) 100%);
  overflow: hidden;
}

.floor {
  position: absolute;
  top: 244px;
  left: 0;
  right: 0;
  bottom: 0;
  background: #232323;
}

.invisible-men {
  animation: fade-in 0.8s ease-out 1s;
  animation-fill-mode: both;
}

.leg {
  position: absolute;
  top: 0;
  left: 147px;
  width: 151px;
  height: 245px;
  transform-origin: 50% 0;
}

.shoe {
  position: absolute;
  width: 151px;
  height: 128px;
  left: 0;
  bottom: 0;
  background: url('https://100dayscss.com/codepen/doc-martens.svg') center center no-repeat;
  transform-origin: 0 95%;
}

.left {
  animation: leg-swing 2s ease-in-out infinite;

  .shoe {
    animation: shoe-turn 2s ease-in-out infinite;
  }
}

.right {
  animation: leg-swing 2s ease-in-out 1s infinite;

  .shoe {
    animation: shoe-turn 2s ease-in-out 1s infinite;
  }
}

@keyframes leg-swing {
  0%,
  100% {
    transform: rotate(-22deg);
  }
  50% {
    transform: rotate(40deg);
  }
}

@keyframes shoe-turn {
  0%,
  100% {
    transform: rotate(-10deg) translateY(-5px) translateX(10px);
  }
  25% {
    transform: rotate(0deg) translateY(0px) translateX(0);
  }
  50% {
    transform: rotate(10deg) translateY(-10px) translateX(10px);
  }
  75% {
    transform: rotate(0deg) translateY(-30px) translateX(0);
  }
}

@keyframes fade-in {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
