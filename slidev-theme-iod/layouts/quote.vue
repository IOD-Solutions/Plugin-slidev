<script setup lang="ts">
defineProps<{
  author?: string
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-quote">
    <div class="quote-content">
      <div class="quote-mark">«</div>
      <div class="quote-text"><slot /></div>
      <div v-if="author" class="quote-author">— {{ author }}</div>
    </div>
    <img src="/iod-logo.png" alt="IoD solutions" class="quote-logo" />
  </div>
</template>
