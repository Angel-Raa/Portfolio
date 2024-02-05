<script setup lang="ts">
import { skills } from '@/cv.json'
</script>

<template>
  <section>
    <h2>Habilidades</h2>
    <ul>
      <li v-for="(it, index) in skills" :key="index">
        <span> {{ it.name }} </span>
      </li>
    </ul>
  </section>
</template>

<style scoped>
ul {
  display: inline-flex;
  gap: 8px;
  flex-wrap: wrap;
}

li {
  border-radius: 6px;
  background: #eee;
  color: black;
  font-size: 0.8rem;
  font-weight: 500;
  padding: 0.2rem 0.6rem;
}
</style>
