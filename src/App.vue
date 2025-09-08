<script setup>
import { ref, onMounted } from 'vue'
import UpdateNotice from './components/UpdateNotice.vue'

// read the query param once on load – no persistence
const debug = ref(false)

onMounted(() => {
  const q = new URLSearchParams(window.location.search).get('debug')
  debug.value = (q === 'true')
})
</script>

<template>
  <!-- Default: show the notice -->
  <UpdateNotice v-if="!debug" />

  <!-- Preview/WIP when ?debug=true -->
  <div v-else>
    <header style="padding:1rem 1.25rem">My Portfolio <small>(preview)</small></header>
    <section style="padding:1.25rem">
      <!-- put your WIP content here -->
      <p>👋 Preview mode enabled. Build in progress…</p>
    </section>
  </div>
</template>
