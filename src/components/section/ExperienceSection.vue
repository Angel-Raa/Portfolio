<script setup lang="ts">
import { work } from '@/cv.json'

const handleFormatDates = (start: string, end: string): string => {
  const startYear = new Date(start).getFullYear()
  const endYear = end != null ? new Date(end).getFullYear() : 'Actual'
  return `${startYear} - ${endYear}`
}
</script>
<template>
  <section>
    <h2>Experiencia laboral</h2>
    <ul v-for="(it, index) in work" :key="index">
      <li>
        <article>
          <header>
            <div>
              <h3>
                <a :href="it.url" :title="`Ver ${it.name}`" target="_blank">
                  {{ it.name }}
                </a>
              </h3>
              <h4>{{ it.position }}</h4>
            </div>
            <time>{{ handleFormatDates(it.startDate, it.endDate) }}</time>
          </header>
          <footer>{{ it.summary }}</footer>
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

article a {
  color: #111;
}

article a:hover {
  text-decoration: underline;
}

article h4 {
  color: #222;
  font-weight: 400;
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
