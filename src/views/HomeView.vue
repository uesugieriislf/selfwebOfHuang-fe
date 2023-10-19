<script setup lang="ts">
</script>

<template>
  <main>
    <div class="logo">
      <!-- <img src="@/assets/home.png" alt="" width="300"> -->
      <div class="logo-word">
        <div class="main-word">
          GAVINHTXXX
        </div>
        <div class="sub-word">
          Welcome, this website is more than a simple portfolio
          . It's a space to get to know more
          about the person behind all of the work.
          Enjoy your exploration journey and get to
          know me better.
        </div>
      </div>
      <RouterLink to="/about">
        <div class="open-button">
          君子可内敛不可懦
        </div>
      </RouterLink>
    </div>
  </main>
</template>
<style lang="less">
main {
  width: calc(100vw - 24px);
  height: calc(100vh - 24px);
  display: flex;
  justify-content: center;
  // align-items: center;
  background: var(--bgHolder);
  border-radius: 12px;
  animation: firstDisplay 3s ease-in-out;
}

@keyframes firstDisplay {
  0% {
    transform: translateY(100%) rotate3d(2, -1, -1, -0.2turn);


  }

  60% {
    border-radius: 12px 12px 50% 50%;
  }

  100% {
    transform: translateY(10) rotate3d(0);
    border-radius: 12px;

  }
}

.logo {
  display: flex;
  flex-direction: column;
  // justify-content: cen ter;
  align-items: center;
  margin-top: 60px;
}

.open-button {
  position: relative;
  width: 160px;
  height: 34px;
  line-height: 34px;
  text-align: center;
  color: var(--dark);
  font-size: 14px;
  background: var(--white);
  cursor: pointer;
  border-radius: 20px;
  /* 添加过渡效果 */
  transition: all 0.5s;
}

.open-button::after,
.open-button::before {
  content: "";
  position: absolute;
  border: 2px solid #55557f;
  width: 155px;
  height: 30px;
  border-radius: 20px;
  inset: 2px 2px;
  animation: pathRotate 3s infinite linear;
}

@keyframes pathRotate {

  0%,
  100% {
    clip-path: inset(0 0 98% 0);
  }

  25% {
    clip-path: inset(0 98% 0 0);
  }

  50% {
    clip-path: inset(98% 0 0 0);
  }

  75% {
    clip-path: inset(0 0 0 98%);
  }
}

.open-button::after {
  animation-delay: -1.5s;
}

.open-button:hover {
  filter: brightness(1.5);
}

.logo-word {
  padding: 20px;
  text-align: center;

  .main-word {
    font-weight: 700;
    font-size: 40px;
    color: var(--color);
  }

  .sub-word {
    color: var(--dark);
    text-align: center;
    font-size: 12px;
    line-height: 1.2;
  }
}
</style>
