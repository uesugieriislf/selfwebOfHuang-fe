<template>
  <div class="about">
    <header>
      <nav>
        <ul>
          <li>
            <RouterLink to="/">Home</RouterLink>
          </li>
          <li>Blog</li>
          <li>Life</li>
        </ul>
      </nav>
    </header>
    <h1>This is an about page</h1>
    <div>
      <div class="g-container">
        <div class="g-inner"></div>
      </div>
    </div>
    <div class="box"></div>
  </div>
</template>

<style>
.about {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  /* animation: firstDisplay 3s ease-in-out; */

}

header {
  width: 100%;
  height: 10vh;
  display: flex;
  justify-content: flex-end;
  align-items: center;

}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

nav ul li {
  padding-left: 10px;
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

.g-container {
  position: relative;
  width: 380px;
  padding-top: 100px;
  filter: contrast(20);
  background-color: #fff;
  overflow: hidden;

  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    backdrop-filter: blur(10px);
    z-index: 1;
  }
}

.g-inner {
  position: relative;
  width: 380px;
  height: 100px;
  background: radial-gradient(circle at 20px 0, transparent, transparent 20px, #000 21px, #000 40px);
  background-size: 80px 100%;
}

.box {
  width: 260px;
  height: 145px;
  background-image: radial-gradient(circle at 10px 10px, transparent 10px, #c366fd 10px, #c366fd 100%);
  background-size: 100% 25px;
  background-position: -10px 25px;
}
</style>
