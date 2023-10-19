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
  </div>
</template>

<style>
.about {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  animation: firstDisplay 3s ease-in-out;

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
</style>
