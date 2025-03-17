<script setup>
import GoodBoi from './components/GoodBoi.vue'
</script>

<template>
  <header>
    <p>dark light mode button</p>
    <div id="page-links-wrapper">
      <p>ABOUT</p>
      <p>LINKS</p>
    </div>
  </header>

  <main>
    <div id="first-page">
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="500" />
    </div>
    <GoodBoi />
  </main>
</template>

<style scoped>
header {
  height: 5rem;
  place-items: center;
  display: flex;
  justify-content: space-between;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  .logo {
    margin: 0 0 9rem 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  #page-links-wrapper {
    display: flex;
    flex-direction: row;
    gap: 2rem;
    margin: 0 1rem;
    font-size: 2rem;
  }

  #first-page {
    width: 100vw;
    height: calc(100vh - 2rem);
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>
