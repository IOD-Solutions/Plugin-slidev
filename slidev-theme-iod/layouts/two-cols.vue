<script setup lang="ts">
defineProps<{
  meta?: string
  sectionTag?: string
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-default">
    <div v-if="sectionTag" class="iod-section-tag">{{ sectionTag }}</div>
    <div class="iod-content">
      <slot name="default-header" />
      <div class="iod-cols-2 flex-1">
        <div><slot /></div>
        <div><slot name="right" /></div>
      </div>
    </div>
    <footer class="iod-footer">
      <img src="/iod-logo.png" alt="IoD solutions" class="logo" />
      <div class="meta">
        <span v-if="meta">{{ meta }}</span>
        <span v-if="meta" class="divider">—</span>
        <span><SlideCurrentNo /> / <SlidesTotal /></span>
      </div>
    </footer>
  </div>
</template>
