<template>
  <div id="app">
    <TheNavigation />
    <transition name="views" mode="out-in">
      <router-view v-bind:key="$route.path" />
    </transition>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TheNavigation from './components/layout/TheNavigation.vue';

export default Vue.extend({
  name: 'App',
  components: {
    TheNavigation
  }
});
</script>

<style lang="scss" scoped>
.views-enter-active,
.views-leave-active {
  transition: all 0.6s cubic-bezier(1, 0.5, 0.8, 1);
}
.views-enter,
.views-leave-to {
  opacity: 0;
  transform: translateX(10px);
}
</style>
