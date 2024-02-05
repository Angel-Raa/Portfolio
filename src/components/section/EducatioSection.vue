<script setup lang="ts">
import { education } from '@/cv.json'
const handleFormatDates = (start: string, end: string | any): string => {
  const startYear = new Date(start).getFullYear()
  const endYear = end != null ? new Date(end).getFullYear() : 'Actual'
  return `${startYear} - ${endYear}`
}
</script>
<template>
  <section>
    <h2>Educación</h2>
    <ul v-for="(it, index) in education" :key="index">
      <li>
        <article>
          <header>
            <div>
              <h3>{{ it.institution }}</h3>
            </div>
            <time>{{ handleFormatDates(it.startDate, it.endDate) }}</time>
          </header>
          <footer>
            <p>{{ it.area }}</p>
          </footer>
        </article>
      </li>
    </ul>
  </section>
</template>
<style scoped>
ul {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

article h3 {
  font-weight: 500;
  color: #111;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 4px;
}

time {
  color: #555;
  font-size: 0.85rem;
  min-width: 102px;
}

@media (width <= 700px) {
  time {
    text-align: right;
  }
}
</style>
