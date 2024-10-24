<script setup lang="ts">
const seaActive = ref(false)
const menuActive = ref(false)
</script>

<template>
  <div class="frame">
    <div class="panel" :class="{ 'show-menu': menuActive }">
      <div class="header">
        <div class="menu-icon" @click="menuActive = !menuActive">
          <div class="top" />
          <div class="bottom" />
          <div class="circle" />
        </div>
        <span class="title">Notifications</span>
        <input type="text" class="search-input" placeholder="Search ..." :class="{ active: seaActive }">
        <i class="fa fa-search search-icon" @click="seaActive = !seaActive" />
      </div>
      <div class="notifications">
        <div class="line" />
        <div class="notification">
          <div class="circle" />
          <span class="time">9:24 AM</span>
          <p><b>John walker</b> posted a photo on you wall. </p>
        </div>
        <div class="notification">
          <div class="circle" />
          <span class="time">8:19 AM</span>
          <p><b>Alice Parker</b> commented your last post.</p>
        </div>
        <div class="notification">
          <div class="circle" />
          <span class="time">Yesterday</span>
          <p><b>Luke Wayne</b> added you as friend.</p>
        </div>
      </div>
    </div>

    <div class="menu" :class="{ active: menuActive }">
      <ul>
        <li><span class="fa fa-dashboard" />Dashboard</li>
        <li><span class="fa fa-user" />Profile</li>
        <li><span class="fa fa-bell" />Notifications</li>
        <li><span class="fa fa-comments" />Messages</li>
        <li><span class="fa fa-gear" />Settings</li>
      </ul>
    </div>
  </div>

  <TheCd to="006" class="op-5" :bt="35" />
  <TheCd to="008" :bt="10" />
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
  background: var(--blue-dark);
  color: #666666;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
}

.panel {
  position: absolute;
  top: 50px;
  left: 50px;
  height: 300px;
  width: 300px;
  z-index: 2;
  background: #fff;
  border-radius: 3px;
  overflow: hidden;
  box-shadow: 10px 10px 15px 0 rgba(0, 0, 0, 0.3);
  transition: all 0.5s ease-in-out;

  &.show-menu {
    transform: translate3d(150px, 0, 0);
  }

  .header {
    width: 100%;
    height: 60px;
    background: var(--blue);

    .menu-icon {
      position: absolute;
      width: 29px;
      height: 15px;
      top: 23px;
      left: 20px;
      cursor: pointer;

      .top,
      .bottom {
        width: 20px;
        height: 3px;
        background: var(--blue-light);
        border-radius: 3px;
        position: absolute;
      }

      .bottom {
        width: 29px;
        bottom: 0;
      }

      .circle {
        width: 7px;
        height: 7px;
        border-radius: 50%;
        background: var(--blue-light);
        position: absolute;
        top: -2px;
        right: 0;
      }
    }

    .title {
      font-size: 15px;
      font-weight: 600;
      display: block;
      text-align: center;
      line-height: 60px;
      color: #fff;
    }

    .search-input {
      box-sizing: border-box;
      position: absolute;
      top: 13px;
      right: 55px;
      width: 230px;
      height: 34px;
      border-radius: 17px;
      border: none;
      background: #fff;
      padding: 0 17px;
      font-size: 13px;
      color: #666;
      transition: all 0.3s ease-in-out;
      transform: translateX(15px);
      opacity: 0;
      pointer-events: none;

      &.focus {
        outline: none;
      }

      &.active {
        transform: translateX(0);
        opacity: 1;
        pointer-events: all;
      }
    }

    .search-icon {
      position: absolute;
      z-index: 2;
      font-size: 21px;
      color: var(--blue-light);
      top: 18px;
      right: 20px;
      transition: all 0.3s ease;
      cursor: pointer;

      &:hover {
        color: #fff;
      }
    }
  }
}

.notifications {
  position: relative;
  height: 100%;
  overflow: hidden;

  .line {
    position: absolute;
    width: 3px;
    top: 0;
    bottom: 0;
    left: 27px;
    background: #ebebeb;
  }

  .notification {
    position: relative;
    margin: 25px 20px 25px 43px;

    &:nth-child(2) {
      animation: here-am-i 0.5s ease-out 0.4s;
      animation-fill-mode: both;
    }

    &:nth-child(3) {
      animation: here-am-i 0.5s ease-out 0.6s;
      animation-fill-mode: both;
    }

    &:nth-child(4) {
      animation: here-am-i 0.5s ease-out 0.8s;
      animation-fill-mode: both;
    }

    &:hover {
      color: var(--blue);
      cursor: pointer;
    }

    .circle {
      box-sizing: border-box;
      width: 11px;
      height: 11px;
      background: #fff;
      border-radius: 50%;
      border: 2px solid var(--blue);
      box-shadow: 0 0 0 3px #fff;
      position: absolute;
      top: 0;
      left: -20px;
    }

    .time {
      display: block;
      font-size: 11px;
      line-height: 11px;
      margin-bottom: 2px;
    }

    p {
      margin: 0;
      font-size: 15px;
      line-height: 20px;
    }

    b {
      font-weight: 600;
    }
  }
}

.menu {
  position: absolute;
  width: 170px;
  height: 270px;
  top: 65px;
  left: 50px;
  background: #43627d;
  border-radius: 3px;
  transition: all 0.5s ease-in-out;
  transform: translate3d(20px, 0, 0);

  &.active {
    box-shadow: 5px 5px 8px 0 rgba(0, 0, 0, 0.2);
    transform: translate3d(0, 0, 0);
  }

  ul {
    margin: 0;
    padding: 10px 0;
  }

  li {
    color: #93b2cd;
    margin: 0;
    padding: 18px 17px;
    list-style: none;
    font-size: 14px;
    line-height: 14px;
    cursor: pointer;
    transition: all 0.3s ease-in-out;

    &:hover {
      color: #fff;
      background: #385269;
    }

    span {
      display: block;
      float: left;
      margin-right: 8px;
      margin-top: -1px;
    }

    .fa-gear,
    .fa-user,
    .fa-bell {
      margin-top: 0;
    }
  }
}

@keyframes here-am-i {
  from {
    transform: translate3d(0, 50px, 0);
    opacity: 0;
  }
  to {
    transform: translate3d(0, 0, 0);
    opacity: 1;
  }
}
</style>
