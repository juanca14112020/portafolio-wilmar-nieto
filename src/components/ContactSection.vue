<script setup>
import SectionBlock from './SectionBlock.vue'
import { profile } from '../data/portfolio'
</script>

<template>
  <SectionBlock id="contacto" title="Contacto">
    <p class="prose">Si buscas a alguien para mantenimiento, diseño mecánico o análisis de datos, escríbeme.</p>
    <ul class="contact">
      <li><span>Correo</span><a :href="`mailto:${profile.email}`">{{ profile.email }}</a></li>
      <li><span>Teléfono</span><a :href="`tel:${profile.phone.replace(/\s/g, '')}`">{{ profile.phone }}</a></li>
      <li><span>Ciudad</span>{{ profile.city }}</li>
    </ul>
    <div class="actions">
      <a class="btn btn-primary" :href="`mailto:${profile.email}`">Enviar correo</a>
      <a class="btn" :href="profile.whatsapp" target="_blank" rel="noopener">Escribir por WhatsApp</a>
    </div>
  </SectionBlock>
</template>