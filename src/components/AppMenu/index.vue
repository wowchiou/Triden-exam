<template>
  <nav class="menu" :class="{ active: toggle }">
    <header class="head">
      <div class="toggle" @click="toggleMenu"><span /></div>
      <h1 class="title">白頭翁不吃小米</h1>
      <a class="logo" />
    </header>
    <ul class="list">
      <li v-for="itm in menuList" :key="itm.title">
        <router-link :to="itm.path" active-class="menu_active">{{ itm.title }}</router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { ref, reactive } from 'vue'

defineOptions({
  name: 'AppMenu',
})

const toggle = ref(false)

const menuList = reactive([
  {
    title: '白頭翁的特性',
    path: '/',
  },
  {
    title: '白頭翁的故事',
    path: '/story',
  },
  {
    title: '白頭翁的美照',
    path: '/photo',
  },
  {
    title: '白頭翁的危機',
    path: '/crisis',
  },
])

function toggleMenu() {
  toggle.value = !toggle.value
}
</script>

<style lang="scss" scoped>
.menu {
  text-align: center;
  box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.25);
  padding: 19.61px 18.84px;
  background-color: #fff;
  position: relative;
  width: 100%;
  z-index: 1;
  @media screen and (min-width: $screen_lg) {
    width: 345px;
    padding: 78.33px 0;
    box-shadow: none;
    min-height: 100vh;
  }
  &.active {
    .toggle {
      span {
        display: none;
      }
      &::after,
      &::before {
        top: 50%;
        left: 50%;
      }
      &::before {
        transform: translate(-50%, -50%) rotate(-45deg);
      }
      &::after {
        transform: translate(-50%, -50%) rotate(45deg);
      }
    }
    .list {
      display: block;
    }
  }
  .head {
    display: flex;
    justify-content: space-between;
    align-items: center;
    @media screen and (min-width: $screen_lg) {
      justify-content: center;
    }
  }
  .toggle {
    width: 24px;
    height: 24px;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    position: relative;
    cursor: pointer;
    @media screen and (min-width: $screen_lg) {
      display: none;
    }
    &::after,
    &::before,
    & span {
      content: '';
      position: absolute;
      width: 100%;
      left: 0;
    }
    &::after,
    &::before,
    & span {
      height: 4px;
      background-color: #000;
    }
    span {
      width: 15.27px;
    }
    &::after {
      top: 0;
    }
    &::before {
      bottom: 0;
    }
  }
  .logo {
    width: 48.78px;
    height: 48.52px;
    border-radius: 9999px;
    box-shadow: 0 0 6px 0 rgba(0, 0, 0, 0.25);
    position: relative;
    background-color: #fff;
    background-image: url('@/assets/images/logo.png');
    background-repeat: no-repeat;
    background-size: 37.98px;
    background-position: center center;
    @media screen and (min-width: $screen_lg) {
      width: 97px;
      height: 97px;
      position: absolute;
      right: 0;
      transform: translateX(50%);
      z-index: 3;
      background-size: 75.96px;
    }
    img {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
  }
  .title {
    font-size: 20px;
    font-weight: 700;
    color: #333;
    @media screen and (min-width: $screen_lg) {
      font-size: 30px;
    }
  }
  .list {
    font-size: 18px;
    display: none;
    @media screen and (min-width: $screen_lg) {
      margin-top: 75.67px;
      display: block !important;
    }
    li {
      &:not(:first-child) {
        margin-top: 17.53px;
        @media screen and (min-width: $screen_lg) {
          margin-top: 21.74px;
        }
      }
      .menu_active {
        color: $color_primary;
        text-decoration: underline;
      }
    }
  }
}
</style>
