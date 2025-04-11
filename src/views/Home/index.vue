<template>
  <main class="home">
    <div class="banner">
      <div class="content">
        <h2 class="title">白頭翁<span>(Chinese bulbul)</span></h2>
        <p class="text">又名白頭鵯。以果實、昆蟲為主食，無法消化小米、穀類。平均壽命約 8~10 年。</p>
      </div>
    </div>

    <div class="info">
      <div v-for="itm in info" :key="itm.title" class="item">
        <h3 class="title">{{ itm.title }}</h3>
        <p class="text">{{ itm.text }}</p>
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'

defineOptions({
  name: 'HomePage',
})

const info = ref([
  {
    title: '外觀',
    text: '白頭鵯體長約17到22公分，額至頭頂純黑色而富有光澤，兩眼上方至後枕白色，形成一白色枕環。耳羽後部有一白斑，此白環與白斑在黑色的頭部均極為醒目，老鳥的枕羽(後頭部)更潔白，所以又叫「白頭翁」。',
  },
  {
    title: '棲地',
    text: '白頭翁和麻雀、綠繡眼合稱「城市三寶」，常成群出現在平原區灌木叢、丘陵樹林地帶，以及校園、公園、庭院、行道中的各種高高的電線與樹上。',
  },
  {
    title: '食性',
    text: '以果樹的漿果和種子為主食，並時常飛入果園偷吃果實，還會吃嫩葉嫩芽，尤其是胡蝶蘭的嫩葉嫩芽葉，偶爾啄食昆蟲。',
  },
])
</script>

<style lang="scss" scoped>
$screen_ipad: 890px;

.home {
  display: flex;
  flex-direction: column;
  background-color: #dcccbc;
  min-height: calc(100vh - 87.73px);
  @media screen and (min-width: $screen_lg) {
    min-height: 100vh;
  }
  .banner {
    background-image: url(./images/banner.jpeg);
    aspect-ratio: 375 / 311.4;
    position: relative;
    background-size: 220%;
    background-position: 65% 50%;
    background-repeat: no-repeat;
    @media screen and (min-width: $screen_md) {
      height: 634.21px;
      background-size: 2034px;
      background-position: -626.6px -234.06px;
    }
    .content {
      flex: 1;
      color: #fff;
      position: absolute;
      bottom: 24.07px;
      right: 0;
      text-align: right;
      padding: 0 22.67px;
      width: 100%;
      @media screen and (min-width: $screen_ipad) {
        padding: 0;
        bottom: 36.85px;
        right: 44.75px;
      }
      .title {
        font-size: 48px;
        font-weight: 700;
        line-height: 1.2;
        @media screen and (min-width: $screen_ipad) {
          line-height: 1.5;
        }
      }
      .text {
        margin-top: 4px;
        font-size: 18px;
        font-weight: 400;
        line-height: 1.5;
      }
    }
  }
  .info {
    padding: 50.86px 36.38px;
    @media screen and (min-width: $screen_ipad) {
      display: flex;
      padding: 50.86px 0;
    }
    .item {
      flex: 1;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 50.5px;
      &:not(:first-child) {
        padding-top: 50.5px;
      }
      @media screen and (min-width: $screen_ipad) {
        gap: 37.84px;
        padding-top: 0;
        &:not(:first-child) {
          padding-top: 0;
        }
      }
      .title {
        font-size: 36px;
        font-weight: 700;
        writing-mode: vertical-lr;
        position: relative;
        &::after {
          content: '';
          position: absolute;
          width: 25px;
          height: 25px;
          border: 8px solid $color_primary;
          border-radius: 50%;
          opacity: 0.6;
          box-sizing: border-box;
          bottom: -11.58px;
          right: -15.94px;
        }
      }
      .text {
        max-width: none;
        line-height: 1.5;
        @media screen and (min-width: $screen_ipad) {
          max-width: 199.66px;
        }
      }
    }
  }
}
</style>
