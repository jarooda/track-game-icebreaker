<script setup lang="ts">
import { ref } from 'vue'

const inputCharacter = ref(0)
const character = ref(0)

const setChar = () => {
  character.value = inputCharacter.value
}
</script>

<template>
  <div class="clues-card">
    <div>
      <input v-model.number="inputCharacter" type="text" placeholder="Set Clues">
      <button @click="setChar">SET CLUES CHAR</button>
      <button @click="character = 0">RESET</button>
    </div>
    <div v-if="character > 0" class="clues-wrapper">
      <input
        v-for="char in character"
        :key="char"
        type="text"
        class="clues-input"
        maxlength="1"
      >
    </div>
  </div>
</template>

<style scoped>
.clues-card {
  padding: 12px;
  border: 1px solid white;
  border-radius: 10px;
}

.clues-wrapper {
  margin-top: 12px;
}

.clues-input {
  width: 100px;
  height: 100px;
  font-size: 5rem;
  text-align: center;
}
</style>