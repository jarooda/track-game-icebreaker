<script setup lang="ts">
import TheCountdown from './components/TheCountdown.vue'
import GroupDetail from './components/GroupDetail.vue'
import TheClues from './components/TheClues.vue'
</script>

<template>
  <div class="main-wrapper">
    <aside>
      <GroupDetail />
    </aside>
    <main>
      <TheCountdown />
    </main>
    <aside>
      <GroupDetail />
    </aside>
  </div>
  <footer>
    <TheClues />
  </footer>
</template>

<style scoped>
.main-wrapper {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: 1fr;
  grid-template-areas: "left main right";
  gap: 12px;
  margin-bottom: 12px;
}
</style>