<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import SectionBlock from './components/SectionBlock.vue'
import TimelineList from './components/TimelineList.vue'
import ContactSection from './components/ContactSection.vue'
import { profile, skills, experience, education } from './data/portfolio'
</script>

<template>
  <NavBar />
  <main>
    <HeroSection />

    <SectionBlock id="perfil" title="Perfil">
      <p v-for="p in profile.about" :key="p" class="prose">{{ p }}</p>
    </SectionBlock>

    <SectionBlock id="habilidades" title="Habilidades">
      <div class="skills">
        <div v-for="s in skills" :key="s.group" class="skill-group">
          <h3>{{ s.group }}</h3>
          <ul>
            <li v-for="i in s.items" :key="i">{{ i }}</li>
          </ul>
        </div>
      </div>
    </SectionBlock>

    <SectionBlock id="experiencia" title="Experiencia">
      <TimelineList :items="experience" />
    </SectionBlock>

    <SectionBlock id="formacion" title="Formación">
      <TimelineList :items="education" />
    </SectionBlock>

    <ContactSection />
  </main>
  <footer class="footer">
    <p>© {{ new Date().getFullYear() }} {{ profile.name }}</p>
  </footer>
</template>