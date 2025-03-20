<script setup>
// import GoodBoi from './components/GoodBoi.vue'
import StarButton from './components/StarButton.vue'
import EventFlyer from './components/EventFlyer.vue'
</script>

<template>
  <!-- <header>
    <p>dark light mode button</p>
    <div id="page-links-wrapper">
      <p>ABOUT</p>
      <p>LINKS</p>
    </div>
  </header> -->

  <main>
    <div id="first-page">
      <div class="column" style="flex-grow: 1">
        <StarButton link="DARKMODE" :rotation="0" rotationGroup="fast" />
        <StarButton link="ABOUT" :rotation="170" rotationGroup="slow" />
      </div>
      <div class="column" style="flex-grow: 1">
        <EventFlyer start-time="6:30" door-time="6:00" next-date="3/11" />
      </div>
      <div class="column" style="flex-grow: 1">
        <StarButton link="HOSTS" :rotation="70" rotationGroup="slow" />
        <StarButton link="LINKS" :rotation="275" rotationGroup="fast" />
      </div>
    </div>
  </main>
</template>

<style scoped>
header {
  height: 5rem;
  justify-content: space-between;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

.column {
  justify-content: center;
  flex-direction: column !important;
  gap: 100px;
}

@media (min-width: 1024px) {
  .logo {
    margin: 0 0 9rem 0;
  }

  header .wrapper {
    flex-wrap: wrap;
  }

  #page-links-wrapper {
    gap: 2rem;
    margin: 0 1rem;
    font-size: 2rem;
  }

  #first-page {
    width: 100vw;
    height: calc(100vh - 2rem);
  }
}
</style>
