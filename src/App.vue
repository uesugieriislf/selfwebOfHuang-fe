<script setup lang="ts">
import { RouterView } from 'vue-router'
</script>

<template>
  <router-view v-slot="{ Component }">
    <Transition name="fly">
      <component :is="Component"></component>
    </Transition>
  </router-view>
</template>
<style scoped>
#app {
  background: #f2f2f0;

}

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
