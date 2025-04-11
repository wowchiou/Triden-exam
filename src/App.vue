<script setup>
import { RouterView } from 'vue-router'
import AppMenu from '@/components/AppMenu/index.vue'
</script>

<template>
  <div class="container">
    <AppMenu class="app_menu" />
    <div class="main">
      <RouterView />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  max-width: 1440px;
  min-width: 375px;
  margin: auto;
  @media screen and (min-width: $screen_lg) {
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
  }
  .main {
    width: 100%;
    flex: 1;
  }
}
</style>
