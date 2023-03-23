<script setup lang="ts">
import { ref } from 'vue'

const count = ref(0)
const inputCount = ref(0)

const tick = () => {
  count.value--
}
const setCountdown = () => {
  count.value = inputCount.value
  // ensure we don't have multiple intervals running
  // ensure count.value will not be negative
  
  const interval = setInterval(tick, 1000)
  setTimeout(() => {
    clearInterval(interval)
  }, count.value * 1000)
}

</script>

<template>
  <div class="countdown-card">
    <div>
      <input v-model="inputCount" type="text" placeholder="Set Countdown">
      <button @click="setCountdown">SET COUNTDOWN</button>
    </div>
    <h1>
      {{ count }}
    </h1>
  </div>
</template>

<style scoped>
.countdown-card {
  padding: 12px;
  border: 1px solid white;
  border-radius: 10px;
}

.countdown-card h1 {
  font-size: 15rem;
  font-weight: 700;
  margin: 0;
  padding: 0;
  text-align: center;
}

.countdown-card div {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>