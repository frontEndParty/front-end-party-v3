<script setup lang="js">
import { ref, computed, onMounted, onUnmounted } from 'vue'

const props = defineProps(['link', 'rotation', 'rotationGroup'])

const link = props.link
const rotation = ref(props.rotation || 0) // Initialize rotation directly

const transformStar = computed(() => `rotate(${rotation.value}deg)`)
const transformText = computed(() => `translate(-50%, -50%) rotate(${rotation.value * -1}deg )`)

// Animation logic
let interval

onMounted(() => {
  let direction = 1
  const delay = props.rotationGroup === 'slow' ? 250 : 0 // Delay slow group by 0.5s

  setTimeout(() => {
    interval = setInterval(() => {
      rotation.value += direction * 5
      direction *= -1
    }, 500)
  }, delay)
})

onUnmounted(() => {
  clearInterval(interval)
})
</script>

<template>
  <a v-bind:href="link" :style="{ transform: transformStar }">
    <img alt="Star" class="star" src="/src/assets/star.svg" width="250" />
    <p :style="{ transform: transformText }">{{ link }}</p>
  </a>
</template>

<style lang="css">
a {
  position: relative;
  margin: 5px;
  transition: transform 0s step-start;
}

p {
  position: absolute;
  top: 50%;
  left: 50%;
  transition: transform 0s step-start;
  font-size: 1.4rem;
}
</style>
