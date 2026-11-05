<script setup>
defineProps({ items: { type: Array, required: true } })
</script>

<template>
  <ol class="timeline">
    <li v-for="i in items" :key="i.title + i.period">
      <span class="period">{{ i.period }}</span>
      <div>
        <h3>{{ i.title }}</h3>
        <p class="place">{{ i.place }}</p>
        <p v-if="i.text" class="prose">{{ i.text }}</p>
      </div>
    </li>
  </ol>
</template>