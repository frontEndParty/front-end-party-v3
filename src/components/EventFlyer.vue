<script setup lang="js">
const { startTime, doorTime, nextDate } = defineProps(['startTime', 'doorTime', 'nextDate'])
</script>

<template>
  <div>
    <img alt="Front End Party Flyer" id="flyer" src="/src/assets/flyer.png" width="500" />
    <p class="start-time">{{ startTime }}</p>
    <p class="door-time">{{ doorTime }}</p>
    <p class="next-date">{{ nextDate }}</p>
  </div>
</template>

<style lang="css">
div {
  position: relative;
}
.start-time {
  position: absolute;
  bottom: 67px;
  left: 295px;
  font-size: 2rem;
  transform: rotate(-4deg);
}
.door-time {
  position: absolute;
  top: 179px;
  left: 402px;
  font-size: 2rem;
  transform: rotate(85deg);
}
.next-date {
  position: absolute;
  bottom: -133px;
  left: 334px;
  font-size: 3.5rem;
}
</style>
