<script setup lang="ts">
import { basics } from '@/cv.json'
import Mail from '../icon/MailIcon.vue'
import Tel from '../icon/TelIcon.vue'
import GitHub from '../icon/GitHub.vue'
import Linkedin from '../icon/LinkedinIcon.vue'
import World from '../icon/worldMapIcon.vue'
import X from '../icon/XIcon.vue'
const { name, label, image, location, profiles, phone, email } = basics
const { city, region } = location
const REDES_SOCIALES: Record<string, any> = {
  Linkedin,
  GitHub,
  X
}

const linkedin = profiles.find(({ network }) => network === 'Linkedin')
const linkedinUrl = linkedin?.url
const printInfo = [email, phone, linkedinUrl].filter(Boolean).join(' • ')
</script>

<template>
  <section>
    <div class="container">
      <div class="info">
        <h1>{{ name }}</h1>
        <p>{{ label }}</p>
        <!---Obtener icon luego --->

        <span> <World /> {{ city }}, {{ region }} </span>
        <footer class="print accesible-info">
          {{ printInfo }}
        </footer>
        <footer class="no-print">
          <a
            v-if="email"
            :href="`mailto:${email}`"
            :title="`Enviar un correo electronico a ${name} al correo ${email}`"
            target="_blank"
          >
            <!---Obtener icon luego --->
            <Mail />
          </a>
          <a
            v-if="phone"
            :href="`tel:${phone}`"
            :title="`Llamar por telefon a ${name} al numero ${phone}`"
            target="_blank"
          >
            <!---Obtener icon luego --->
            <Tel />
          </a>
          <a
            v-for="(profile, index) in profiles"
            :key="index"
            :href="profile.url"
            target="_blank"
            rel="noopener noreferrer"
            :title="`Visitar el perfil de ${profile.username} en ${profile.network}`"
          >
            <component :is="REDES_SOCIALES[profile.network]" />
          </a>
        </footer>
      </div>
      <figure>
        <img v-bind:src="image" :alt="name" />
      </figure>
    </div>
  </section>
</template>

<style scoped>
h1 {
  font-size: 2rem;
}

.info {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  padding-right: 32px;
}

h2 {
  color: #444;
  font-weight: 500;
  font-size: 1.1rem;
  text-wrap: balance;
}

img {
  aspect-ratio: 1/1;
  object-fit: cover;
  width: 128px;
  border-radius: 6px;
}

.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

span {
  color: #666;
  display: flex;
  align-items: center;
  gap: 0.25rem;
  font-size: 0.85rem;
  letter-spacing: -0.05rem;
}
footer {
  font-size: 0.75rem;
  display: flex;
  gap: 6px;
  margin-top: 8px;
  color: #666;
}

footer a {
  color: #777;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border: 1px solid #eee;
  padding: 4px;
  height: 32px;
  width: 32px;
  border-radius: 6px;
  transition: all 0.3s ease;
}

footer a:hover {
  background-color: #eee;
  border: 1px solid #666;
}
</style>
