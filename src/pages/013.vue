<script setup lang="ts">
const list = [
  { url: 'https://100dayscss.com/codepen/13-1.jpg' },
  { url: 'https://100dayscss.com/codepen/13-2.jpg' },
  { url: 'https://100dayscss.com/codepen/13-3.jpg' },
  { url: 'https://100dayscss.com/codepen/13-4.jpg' },
]

const active = ref(false)
</script>

<template>
  <div class="frame">
    <div v-for="(e, key) in list" :id="`profile-${key}`" :key class="profile" @click="active = !active">
      <img :src="e.url" alt="jpg">
      <div class="overlay" />
      <div class="plus" />
    </div>
    <div id="detail-1" class="detail" :class="{ active }">
      <div class="close" @click="active = !active" />
      <img class="header" src="https://100dayscss.com/codepen/13-1-header.jpg" alt="header">
      <div class="image">
        <img src="https://100dayscss.com/codepen/13-1.jpg" alt="jpg">
      </div>
      <div class="infos">
        <div class="name">
          Juli Toth
        </div>
        <div class="action">
          <div class="btn">
            <span class="fa fa-phone" />
          </div>
          <div class="btn">
            <span class="fa fa-comment" />
          </div>
          <div class="btn">
            <span class="fa fa-heart" />
          </div>
        </div>
      </div>
    </div>
  </div>
  <TheCd to="012" class="op-5" :bt="35" />
  <TheCd to="014" :bt="10" />
</template>

<style scoped>
.frame {
  position: absolute;
  width: 400px;
  height: 400px;
  top: 50%;
  left: 50%;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  background: white;
  color: white;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.profile {
  position: relative;
  float: left;
  width: 194px;
  height: 194px;
  margin: 4px 0 0 4px;
  cursor: pointer;

  .overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: #000;
    opacity: 0;
    transition: all 0.6s ease-in-out;
  }

  .plus {
    position: absolute;
    width: 50px;
    height: 50px;
    top: 50%;
    left: 50%;
    margin: -25px 0 0 -25px;
    background: var(--red);
    border-radius: 50%;
    box-shadow: 2px 4px 10px 0 rgba(0, 0, 0, 0.5);
    transition: all 0.4s ease-in-out;
    opacity: 0;
    transform: scale(2);
    pointer-events: none;

    &:before {
      position: absolute;
      content: '';
      width: 14px;
      height: 2px;
      top: 24px;
      left: 18px;
      background: #fff;
    }

    &:after {
      position: absolute;
      content: '';
      width: 2px;
      height: 14px;
      top: 18px;
      left: 24px;
      background: #fff;
    }
  }

  &:hover {
    .plus {
      opacity: 1;
      transform: scale(1) translate3d(0, 0, 0);
    }

    .overlay {
      opacity: 0.4;
    }
  }
}

.detail {
  display: none;
  position: absolute;
  z-index: 2;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  pointer-events: none;
  font-size: 0;

  &.active {
    pointer-events: all;

    .header {
      transform: translate3d(0, 0, 0);
      transition: all 0.6s ease-out;
    }

    .image {
      transform: translate3d(0, 0, 0);
      transition: all 0.6s ease-out 0.3s;
    }

    .infos {
      transform: translate3d(0, 0, 0);
      transition: all 0.6s ease-out;
    }

    .close {
      transform: rotate(45deg) translate3d(0, 0, 0);
      transition:
        background 0.3s ease-in-out,
        all 0.6s ease-out;
    }
  }

  .close {
    position: absolute;
    z-index: 2;
    width: 50px;
    height: 50px;
    top: 10px;
    right: 10px;
    background: var(--red);
    border-radius: 50%;
    transition:
      background 0.3s ease-in-out,
      all 0.5s ease-in;
    transform: rotate(45deg) translate3d(-105%, -105%, 0);
    cursor: pointer;

    &:before {
      position: absolute;
      content: '';
      width: 14px;
      height: 2px;
      top: 24px;
      left: 18px;
      background: #fff;
      transition: all 0.3s ease-in-out;
    }

    &:after {
      position: absolute;
      content: '';
      width: 2px;
      height: 14px;
      top: 18px;
      left: 24px;
      background: #fff;
      transition: all 0.3s ease-in-out;
    }

    &:hover {
      background: #fff;

      &:after,
      &:before {
        background: var(--red);
      }
    }
  }
}

.header {
  transform: translate3d(0, -105%, 0);
  transition: all 0.6s ease-in 0.4s;
}

.image {
  box-sizing: border-box;
  position: absolute;
  z-index: 1;
  top: 130px;
  left: 150px;
  width: 100px;
  height: 100px;
  border: 2px solid #fff;
  border-radius: 50%;
  overflow: hidden;
  box-shadow: 4px 6px 15px 0 rgba(0, 0, 0, 0.2);
  transform: translate3d(0, -250px, 0);
  transition: all 0.6s ease-in 0.2s;

  img {
    width: 100%;
    height: auto;
  }
}

.infos {
  box-sizing: border-box;
  background: var(--red);
  height: 220px;
  padding-top: 67px;
  transform: translate3d(0, 105%, 0);
  transition: all 0.6s ease-in 0.4s;
}

.name {
  font-size: 16px;
  font-weight: 600;
  text-align: center;
}

.action {
  margin-top: 35px;
  text-align: center;

  .btn {
    position: relative;
    box-sizing: border-box;
    display: inline-block;
    width: 45px;
    height: 45px;
    border: 1px solid #fff;
    margin: 0 20px;
    border-radius: 45px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;

    &:hover {
      background: #fff;
      color: var(--red);
      box-shadow: 2px 3px 6px 0 rgba(0, 0, 0, 0.2);
    }

    .fa {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      text-align: center;
      line-height: 20px;
      font-size: 19px;
      padding-top: 12px;
    }

    .fa-phone {
      font-size: 22px;
    }

    .fa-comment {
      font-size: 20px;
      padding-top: 10px;
      left: 2px;
    }

    .fa-heart {
      top: 1px;
      left: 2px;
    }
  }
}

#detail-1 {
  display: block;
}
</style>
