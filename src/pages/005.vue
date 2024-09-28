<script setup lang="ts">

</script>

<template>
  <div class="frame">
    <div class="card">
      <div class="header">
        <div class="title big">
          Weekly report
        </div>
        <div class="date small">
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
</template>

<style  scoped>
@import url('../styles/005.css');
</style>
