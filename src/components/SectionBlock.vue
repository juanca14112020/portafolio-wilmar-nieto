<script setup>
defineProps({ id: String, title: String })
</script>

<template>
  <section :id="id" class="block">
    <h2>{{ title }}</h2>
    <div class="block-body"><slot /></div>
  </section>
</template>