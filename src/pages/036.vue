<script setup lang="ts">
</script>

<template>
  <div class="frame">
    <div class="center">
      <div class="tabs">
        <div class="top" />

        <input id="tab-1" type="radio" name="rd" checked>
        <label class="tab" for="tab-1">
          <span class="fa fa-eye" />
        </label>

        <input id="tab-2" type="radio" name="rd">
        <label class="tab" for="tab-2">
          <span class="fa fa-comments" />
        </label>

        <input id="tab-3" type="radio" name="rd">
        <label class="tab" for="tab-3">
          <span class="fa fa-bell" />
        </label>

        <input id="tab-4" type="radio" name="rd">
        <label class="tab" for="tab-4">
          <span class="fa fa-cog" />
        </label>

        <label class="tab search">
          <span class="fa fa-search" />
        </label>

        <div class="content">
          <div id="box-1" class="box">
            <h1>Dashboard</h1>
            <p>
              <span style="width: 250px;" />
              <span style="width: 270px;" />
              <span style="width: 235px;" />
              <span style="width: 260px;" />
              <span style="width: 53px;" />
            </p>
            <p>
              <span style="width: 262px;" />
              <span style="width: 234px;" />
              <span style="width: 246px;" />
              <span style="width: 260px;" />
              <span style="width: 144px;" />
            </p>
          </div>

          <div id="box-2" class="box">
            <h1>Comments</h1>
            <p>
              <span style="width: 250px;" />
              <span style="width: 270px;" />
              <span style="width: 235px;" />
              <span style="width: 260px;" />
              <span style="width: 53px;" />
            </p>
            <p>
              <span style="width: 262px;" />
              <span style="width: 234px;" />
              <span style="width: 246px;" />
              <span style="width: 260px;" />
              <span style="width: 144px;" />
            </p>
          </div>

          <div id="box-3" class="box">
            <h1>Notifications</h1>
            <p>
              <span style="width: 250px;" />
              <span style="width: 270px;" />
              <span style="width: 235px;" />
              <span style="width: 260px;" />
              <span style="width: 53px;" />
            </p>
            <p>
              <span style="width: 262px;" />
              <span style="width: 234px;" />
              <span style="width: 246px;" />
              <span style="width: 260px;" />
              <span style="width: 144px;" />
            </p>
          </div>

          <div id="box-4" class="box">
            <h1>Settings</h1>
            <p>
              <span style="width: 250px;" />
              <span style="width: 270px;" />
              <span style="width: 235px;" />
              <span style="width: 260px;" />
              <span style="width: 53px;" />
            </p>
            <p>
              <span style="width: 262px;" />
              <span style="width: 234px;" />
              <span style="width: 246px;" />
              <span style="width: 260px;" />
              <span style="width: 144px;" />
            </p>
          </div>
        </div>
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
  background: #2b3642;
  font-family: 'Open Sans', Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.center {
  position: absolute;
  width: 320px;
  height: 240px;
  top: 80px;
  left: 40px;
  background: #fff;
  box-shadow: 4px 8px 12px 0 rgba(0, 0, 0, 0.3);

  .top {
    position: absolute;
    z-index: 1;
    top: 0;
    left: 0;
    right: 0;
    height: 40px;
    background: #3d4d5e;
  }

  input[type='radio'] {
    display: none;
  }

  .tab {
    position: relative;
    float: left;
    z-index: 5;
    width: 40px;
    height: 40px;
    text-align: center;
    line-height: 3;
    color: #8398ad;
    cursor: pointer;
    font-size: 14px;
    transition: background 0.5s ease-in-out;

    &.search {
      float: right;
    }

    &:hover {
      color: #fff;
    }
  }

  input[type='radio']:checked + .tab {
    background: #5da2ed;
    color: #fff;
  }

  .content {
    position: absolute;
    top: 40px;
    color: #000;

    .box {
      position: absolute;
      top: 0;
      left: 0;
      opacity: 0;
      transform: translateY(3px);
      pointer-events: none;
      padding: 25px;
      transition: all 0.3s ease-in;

      h1 {
        font-weight: 400;
        font-size: 16px;
        color: #415868;
        margin: 0;
        padding: 0;
      }

      p {
        margin: 17px 0;

        span {
          display: block;
          height: 4px;
          background: #e9e9e9;
          margin: 6px 0;
        }
      }
    }
  }
}
#tab-1:checked ~ .content #box-1,
#tab-2:checked ~ .content #box-2,
#tab-3:checked ~ .content #box-3,
#tab-4:checked ~ .content #box-4 {
  pointer-events: all;
  opacity: 1;
  transform: translateY(0);
  transition: all 0.5s ease-out 0.4s;
}
</style>
