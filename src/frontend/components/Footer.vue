<template>
  <footer class="footer status-bar">
    <span>{{ version }}</span>
    <span>Powered by <a href="https://github.com/huilang-me/CF-Server-Monitor" target="_blank">CF-Server-Monitor</a></span>
  </footer>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { fetchConfig } from '../utils/api'

const version = ref('')

onMounted(async () => {
  const config = await fetchConfig()
  if (config && config.version) {
    version.value = config.version
  }
})
</script>