<script setup lang="ts">
</script>

<template>
  <main>
    <div class="logo">
      <img src="@/assets/home.png" alt="" width="400">
      <RouterLink to="/home">君子可内敛不可懦</RouterLink>
    </div>
  </main>
</template>
<style>
main {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>