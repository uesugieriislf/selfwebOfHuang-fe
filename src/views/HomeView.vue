<script setup lang="ts">
import { onMounted } from 'vue';

onMounted(() => {
  const bgTop = document.querySelector('.bg-top')
  window.onscroll = e => {
    let scrollTop = (e.target as Document).scrollingElement?.scrollTop
    console.log(scrollTop);
    bgTop.style.transform = `translateY(${-scrollTop}px)`
  }
})
const open = () => {
  const bgTop = document.querySelector('.bg-top')
  bgTop.style.transform = `translateY(-75vh)`
  bgTop.style.transition = '1s ease-in'

}
</script>

<template>
  <main>
    <div class="bg-top">
      <div class="open" @click="open">
        click to open
      </div>
      <div class="line"></div>
    </div>
    <div class="logo">
      <div class="box"></div>
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
  width: 100vw;
  height: 300vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--bgHolder);
  border-radius: 12px;
  // animation: firstDisplay 3s ease-in-out;
  background: linear-gradient(90deg, #ffc700 0%, #e91e1e 33%, #6f27b0 66%, #00ff88 100%);
  background-position: 100% 0;
  animation: bgSize 5s infinite ease-in-out alternate;
}

@keyframes bgSize {
  0% {
    background-size: 300% 100%;
  }

  100% {
    background-size: 100% 100%;
  }
}

main::after {}

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

.bg-top {
  width: 100vw;
  height: 75vh;
  background: blue;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 100;
  background: linear-gradient(90deg, #ffc700 0%, #e91e1e 33%, #6f27b0 66%, #00ff88 100%);
  background-position: 100% 0;
  animation: bgSize 5s infinite ease-in-out alternate;

  .open {
    width: 100px;
    height: 100px;
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    background: var(--dark);
    color: var(--white);
    cursor: pointer;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .line {
    width: 60%;
    height: 5px;
    background: #000;
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
  }
}

.logo {
  --logoWidth: 250px;
  --logoHeight: 60vh;
  position: fixed;
  left: 50%;
  top: 50%;
  display: flex;
  flex-direction: column;
  // justify-content: cen ter;
  align-items: center;
  width: var(--logoWidth);
  height: var(--logoHeight);
  // background: red;


  transform: translate(-50%, -50%);

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

  .box {
    position: fixed;
    top: 30px;
    z-index: -10;
    width: var(--logoHeight);
    height: var(--logoWidth);
    background-image: radial-gradient(circle at 11px 12px, transparent 7px, #fff 4px, #fff 100%);
    background-size: 100% 20px;
    background-position: -10px 25px;
    transform: rotate(90deg);
  }


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
</style>
