<script setup lang="ts">
import { projects } from '@/cv.json'
</script>
<template>
  <section>
    <h2>Proyectos</h2>
    <ul>
      <li v-for="(it, index) in projects" :key="index">
        <article>
          <header>
            <h3>
              <a
                :href="it.url"
                :title="`Ver el proyecto ${it.name}`"
                target="_blank"
                rel="noopener noreferrer"
              >
                {{ it.name }}
                <span v-if="it.isActive">&bull;</span>
              </a>
            </h3>
            <p>{{ it.description }}</p>
          </header>
          <footer v-for="(text, index) in it.highlights" :key="index">
            <span>{{ text }}</span>
          </footer>
        </article>
      </li>
    </ul>
  </section>
</template>

<style scoped>
ul {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin-inline: -16px;
}

article {
  border-radius: 8px;
  border: 1px solid #f2f2f2;
  gap: 16px;
  display: flex;
  flex-direction: column;
  padding: 16px;
  height: 100%;
}

article header {
  flex: 1;
}

article h3 {
  margin-bottom: 4px;
}

article a {
  color: #111;
}

article a:hover {
  text-decoration: underline;
}

article p {
  font-size: 0.75rem;
  line-height: 1.2rem;
  margin-bottom: 4px;
}

article h3 span {
  color: rgb(0, 188, 47);
}

footer {
  display: flex;
  flex-wrap: wrap;
  gap: 4px;
  font-size: 0.6rem;
}

footer span {
  border-radius: 6px;
  background: #eee;
  color: #444;
  font-size: 0.6rem;
  font-weight: 500;
  padding: 0.2rem 0.6rem;
}

.github-code-link {
  margin-left: 5px;
}

@media (width <= 700px) {
  ul {
    margin-inline: 0px;
  }

  article {
    border: none;
    box-shadow: 0 1px 1px #f2f2f2;
    padding: 0 0 16px 0;
  }
}
</style>
