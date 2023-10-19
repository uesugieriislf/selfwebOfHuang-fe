<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <router-view v-slot="{ Component }">
    <!-- <Transition> -->
    <component :is="Component"></component>
    <!-- </Transition> -->
  </router-view>
</template>
<style scoped>
.fly-enter-from {
  transform: scale(0);
}

.fly-enter-to {
  transform: scale(100%);
}

.fly-enter-active {
  transition: 0.67s ease;
}
</style>
