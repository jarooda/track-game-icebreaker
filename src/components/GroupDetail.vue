<script setup lang="ts">
import { ref } from 'vue'

const score = ref(0)

// add score 100
// minus score -50

const addScore = () => {
  score.value += 100
}

const minusScore = () => {
  score.value -= 50
}
</script>

<template>
  <div class="group-card">
    <div class="group-section">
      <h1>Member</h1>
      <textarea name="member-list" id="member-list" cols="30" rows="10"></textarea>
    </div>
    <div class="group-section">
      <h1>Score</h1>
      <div class="score-wrapper">
        <button @click="minusScore">-</button>
        <h1>{{ score }}</h1>
        <button @click="addScore">+</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.score-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 12px;
}

.score-wrapper h1 {
  font-size: 3rem;
  font-weight: 700;
  margin: 0;
  padding: 0;
  text-align: center;
}

.score-wrapper button {
  width: 80px;
  height: 80px;
  font-size: 5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  margin: 0;
  cursor: pointer;
}

.group-card {
  padding: 12px;
  border: 1px solid white;
  border-radius: 10px;
}

.group-section {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
}
</style>