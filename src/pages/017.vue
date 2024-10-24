<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="stripes">
      <div v-for="i in 30" :key="i" class="stripe" />
    </div>
    <div class="center">
      <svg class="polygon">
        <polygon class="middle" points="68,0 91,0 160,117 46,117 59,93 121,93" />
        <polygon class="dark" points="68,41 79,59 46,117 160,117 147,160 11,140" />
        <polygon class="light" points="0,117 68,0 121,93 98,93 68,41 11,140" />
      </svg>
    </div>
  </div>
  <TheCd to="016" class="op-5" :bt="35" />
  <TheCd to="018" :bt="10" />
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
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  background: #fff;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
}

.stripes {
  position: relative;
  top: -67px;
  left: -100px;
  width: 600px;
  transform: rotate(45deg);

  .stripe {
    background: #353535;
    width: 600px;
    height: 3px;
    margin-bottom: 16px;
  }
}

.center {
  position: absolute;
  width: 260px;
  height: 260px;
  top: 70px;
  left: 70px;
  background: #353535;
  border-radius: 3px;
  box-shadow: 8px 10px 15px 0 rgba(0, 0, 0, 0.3);
}

.polygon {
  position: absolute;
  width: 160px;
  height: 140px;
  top: 60px;
  left: 50px;

  .light {
    fill: #eee;
    transition: all 0.5s ease-in-out;
  }

  .middle {
    fill: #ccc;
    transition: all 0.5s ease-in-out;
  }

  .dark {
    fill: #aaa;
    transition: all 0.5s ease-in-out;
  }

  &:hover {
    .light {
      fill: #aaa;
    }

    .middle {
      fill: #eee;
    }

    .dark {
      fill: #ccc;
    }
  }
}
</style>
