<script setup>
import { ref } from 'vue'
import { profile } from '../data/portfolio'

const open = ref(false)
const links = [
  { href: '#perfil', label: 'Perfil' },
  { href: '#habilidades', label: 'Habilidades' },
  { href: '#experiencia', label: 'Experiencia' },
  { href: '#formacion', label: 'Formación' },
  { href: '#contacto', label: 'Contacto' }
]
</script>

<template>
  <header class="nav">
    <div class="nav-inner">
      <a href="#inicio" class="brand">{{ profile.shortName }}</a>
      <button class="nav-toggle" :aria-expanded="open" aria-controls="menu" @click="open = !open">
        {{ open ? 'Cerrar' : 'Menú' }}
      </button>
      <nav id="menu" :class="{ open }">
        <a v-for="l in links" :key="l.href" :href="l.href" @click="open = false">{{ l.label }}</a>
      </nav>
    </div>
  </header>
</template>