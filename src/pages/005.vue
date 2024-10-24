<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="card">
      <div class="header">
        <div class="big title">
          Weekly report
        </div>
        <div class="small date">
          01. Feb - 07. Feb
        </div>
        <div class="small type">
          Revenue
        </div>
        <div class="big value">
          $ 3621.79
        </div>
      </div>
      <div class="parameter">
        <span class="red">Views</span>
        <span class="blue">Purchases</span>
      </div>
      <div class="statistic">
        <div class="line l1" />
        <div class="line l2" />
        <div class="line l3" />
        <div class="red data">
          <svg>
            <polyline
              points="9,46 50,12 90,23 130,11 171,38 211,48 251,19"
            />
          </svg>
          <div class="points">
            <div class="point p1">
              <div class="tooltip">
                458
              </div>
            </div>
            <div class="point p2">
              <div class="tooltip">
                812
              </div>
            </div>
            <div class="point p3">
              <div class="tooltip">
                746
              </div>
            </div>
            <div class="point p4">
              <div class="tooltip">
                877
              </div>
            </div>
            <div class="point p5">
              <div class="tooltip">
                512
              </div>
            </div>
            <div class="point p6">
              <div class="tooltip">
                434
              </div>
            </div>
            <div class="point p7">
              <div class="tooltip">
                458
              </div>
            </div>
          </div>
        </div>
        <div class="data blue">
          <svg>
            <polyline
              points="9,61 50,50 90,65 130,55 171,61 211,74 251,64"
            />
          </svg>
          <div class="points">
            <div class="point p1">
              <div class="tooltip">
                26
              </div>
            </div>
            <div class="point p2">
              <div class="tooltip">
                41
              </div>
            </div>
            <div class="point p3">
              <div class="tooltip">
                22
              </div>
            </div>
            <div class="point p4">
              <div class="tooltip">
                36
              </div>
            </div>
            <div class="point p5">
              <div class="tooltip">
                25
              </div>
            </div>
            <div class="point p6">
              <div class="tooltip">
                13
              </div>
            </div>
            <div class="point p7">
              <div class="tooltip">
                20
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="days">
        <div class="day">
          Mon
        </div>
        <div class="day">
          Tur
        </div>
        <div class="day">
          Wed
        </div>
        <div class="day">
          Thu
        </div>
        <div class="day">
          Fri
        </div>
        <div class="day">
          Sat
        </div>
        <div class="day">
          Sun
        </div>
      </div>
    </div>
  </div>
  <TheCd to="004" class="op-5" :bt="35" />
  <TheCd to="006" :bt="10" />
</template>

<style  scoped>
.frame {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 400px;
  height: 400px;
  margin-top: -200px;
  margin-left: -200px;
  border-radius: 3px;
  background: #42a7a1;
  box-shadow: 1px 2px 10px 0 rgba(0, 0, 0, 0.3);
  color: white;
  font-family: 'Open Sans', Helvetica, sans-serif;
}

.card {
  width: 280px;
  height: 220px;
  border-radius: 3px;
  background: #fff;
  margin: 90px auto;
  box-shadow: 10px 10px 15px 0 rgba(0, 0, 0, 0.3);
  overflow: hidden;
}

.header {
  width: 100%;
  height: 60px;
  background: #f1ba64;

  position: relative;

  .big {
    position: absolute;
    font-size: 14px;
    font-weight: 600;
  }

  .small {
    position: absolute;
    font-size: 11px;
    font-weight: 400;
  }

  .title {
    top: 12px;
    left: 15px;
  }

  .date {
    top: 30px;
    left: 15px;
  }

  .type {
    top: 14px;
    right: 15px;
  }

  .value {
    top: 28px;
    right: 15px;
  }
}

.parameter {
  text-align: right;
  padding: 10px 0 14px 0;

  span {
    color: #555;
    font-size: 9px;
    line-height: 13px;
    position: relative;
    padding: 0 10px 0 25px;
  }

  span::before {
    content: ' ';
    display: block;
    width: 11px;
    height: 3px;
    position: absolute;
    left: 6px;
    top: 3px;
    background: #000;
    border-radius: 3px;
  }

  .red::before {
    background: #fa7373;
  }

  .blue::before {
    background: #7ba2ff;
  }
}

.statistic {
  width: 260px;
  height: 81px;
  margin: 0 auto;
  position: relative;

  .line {
    width: 100%;
    height: 1px;
    background: #eee;
    position: absolute;
  }

  .l2 {
    top: 50%;
  }

  .l3 {
    bottom: 0;
  }
}

.data {
  svg {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
  }

  polyline {
    fill: none;
    stroke: #000;
    stroke-width: 2;
    stroke-linecap: round;
  }

  &.red polyline {
    stroke: #fa7373;
  }

  &.blue polyline {
    stroke: #7ba2ff;
  }

  .points {
    position: relative;
  }

  .point {
    width: 6px;
    height: 6px;
    border-radius: 3px;
    cursor: pointer;
    position: absolute;
    z-index: 10;
    background: #000;

    &:hover .tooltip {
      visibility: visible;
      opacity: 1;
      transform: translate3d(-50%, 0, 0);
    }
  }

  &.red {
    .point {
      background: #fa7373;
    }

    .p1 {
      position: absolute;
      left: 7px;
      top: 43px;
    }

    .p2 {
      left: 47px;
      top: 10px;
    }

    .p3 {
      left: 87px;
      top: 20px;
    }

    .p4 {
      left: 127px;
      top: 9px;
    }

    .p5 {
      left: 167px;
      top: 35px;
    }

    .p6 {
      left: 207px;
      top: 45px;
    }

    .p7 {
      left: 247px;
      top: 16px;
    }
  }

  &.blue {
    .point {
      background: #7ba2ff;
    }

    .p1 {
      left: 7px;
      top: 58px;
    }

    .p2 {
      left: 47px;
      top: 48px;
    }

    .p3 {
      left: 87px;
      top: 62px;
    }

    .p4 {
      left: 127px;
      top: 52px;
    }

    .p5 {
      left: 167px;
      top: 58px;
    }

    .p6 {
      left: 207px;
      top: 71px;
    }

    .p7 {
      left: 247px;
      top: 61px;
    }
  }

  .tooltip {
    position: absolute;
    bottom: 13px;
    left: 50%;
    transform: translate3d(-50%, 10%, 0);
    padding: 8px 6px;
    border-radius: 3px;
    font-size: 11px;
    line-height: 11px;
    visibility: hidden;
    opacity: 0;
    transition:
      transform 0.4s ease-out,
      opacity 0.4s ease-out 0s;

    &::after {
      content: ' ';
      display: block;
      width: 6px;
      height: 6px;
      position: absolute;
      left: 50%;
      margin-left: -3px;
      bottom: -3px;
      transform: rotate(45deg);
    }
  }

  &.red {
    .tooltip {
      background: #fa7373;

      &:after {
        background: #fa7373;
      }
    }
  }

  &.blue {
    .tooltip {
      background: #7ba2ff;
    }
    &:after {
      background: #7ba2ff;
    }
  }
}

.days {
  width: 280px;
  margin: 0 auto;

  .day {
    float: left;
    width: 40px;
    color: #999;
    font-size: 9px;
    line-height: 30px;
    text-align: center;
  }
}
</style>
