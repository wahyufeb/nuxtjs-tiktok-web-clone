<template>
  <div class="wrapper">
    <div class="wrapper__nav">
      <Navbar />
    </div>
    <div class="wrapper__app">
      <Nuxt />
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

.wrapper__nav {
  border-bottom: 1px solid var(--secondary-color);
  display: flex;
  justify-content: center;
  padding: 6px 0;
}

.wrapper__app {
  display: flex;
  justify-content: center;
  padding: 5px 0;
}
</style>
