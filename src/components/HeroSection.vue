<script setup>
import { ref } from 'vue'
import { profile } from '../data/portfolio'

const photoOk = ref(true)
</script>

<template>
  <section id="inicio" class="hero">
    <div class="hero-text">
      <h1>{{ profile.name }}</h1>
      <p class="hero-sub">{{ profile.headline }}</p>
      <div class="actions">
        <a class="btn btn-primary" href="#contacto">Contactar</a>
        <a class="btn" :href="profile.cv" download>Descargar hoja de vida</a>
      </div>
    </div>

    <aside class="titleblock" aria-label="Datos del ingeniero">
      <div class="avatar">
        <img v-if="photoOk" :src="profile.photo" :alt="`Foto de ${profile.name}`" @error="photoOk = false" />
        <span v-else>{{ profile.initials }}</span>
      </div>
      <dl>
        <div><dt>Programa</dt><dd>{{ profile.role }}</dd></div>
        <div><dt>Universidad</dt><dd>{{ profile.university }}</dd></div>
        <div><dt>Avance</dt><dd>{{ profile.status }}</dd></div>
        <div><dt>Enfoque</dt><dd>{{ profile.focus }}</dd></div>
        <div><dt>Ciudad</dt><dd>{{ profile.city }}</dd></div>
      </dl>
    </aside>
  </section>
</template>