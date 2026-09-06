<script setup>
import { data } from '../data/MainView_data.js'
import { computed } from 'vue'
import capStar from '../assets/otmink-next/cap-star.svg'

const rank = computed(() => String(data.value.ranking).padStart(2, '0'))
</script>

<template>
  <div class="main-rank">
    <div class="rank-shadow">{{ rank }}</div>
    <div class="rank">{{ rank }}</div>
    <div class="cap">
      <span class="cap-star" :style="{ '--cap-star-mask': `url(${capStar})` }"></span>
      <span>[ CAP ] - 社群关注指数</span>
    </div>
    <div class="points">{{ data.score }}</div>
    <div class="rank-title"></div>
  </div>
</template>

<style lang="scss" scoped>
.main-rank {
  position: relative;
  width: 320px;
  height: 800px;
  color: #212121;
}

.rank {
  position: absolute;
  top: 180px;
  left: 14px;
  color: v-bind('data.light_color');
  font-family: 'Bebas Neue', 'Arial Narrow', sans-serif;
  font-size: 470px;
  font-weight: 400;
  line-height: 1;
  letter-spacing: -23.5px;
}

.rank-shadow {
  position: absolute;
  top: 140px;
  left: -58px;
  color: transparent;
  font-family: 'Bebas Neue', 'Arial Narrow', sans-serif;
  font-size: 470px;
  line-height: 1;
  letter-spacing: -23.5px;
  -webkit-text-stroke: 1px rgba(33, 33, 33, 0.2);
}

.rank-title {
  position: absolute;
  top: 640px;
  left: 36px;
  font-size: 20px;
  letter-spacing: -0.65px;
  color: v-bind('data.light_color');
}

.points {
  position: absolute;
  top: 642px;
  left: 33px;
  width: 248px;
  font-family: 'Outfit', 'HarmonyOS Sans SC', sans-serif;
  font-size: 96px;
  line-height: 1.2;
  letter-spacing: -4.8px;
  border-bottom: 1px solid #929292;
}

.cap {
  position: absolute;
  top: 601px;
  left: 35px;
  display: flex;
  align-items: center;
  gap: 6px;
  font-family: 'Geist', 'HarmonyOS Sans SC', sans-serif;
  font-size: 20px;
  letter-spacing: -0.8px;

  .cap-star {
    display: block;
    width: 24px;
    height: 24px;
    background: v-bind('data.light_color');
    mask-image: var(--cap-star-mask);
    mask-repeat: no-repeat;
    mask-position: center;
    mask-size: contain;
    -webkit-mask-image: var(--cap-star-mask);
    -webkit-mask-repeat: no-repeat;
    -webkit-mask-position: center;
    -webkit-mask-size: contain;
  }
}
</style>
