<script setup lang="ts">
import { basics } from '@/cv.json'
const { summary } = basics
</script>

<template>
  <section>
    <h2>Sobre mi</h2>
    <p>{{ summary }}</p>
  </section>
</template>
