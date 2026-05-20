<script setup lang="ts">
defineProps<{
  meta?: string
  sectionTag?: string
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-statement">
    <div v-if="sectionTag" class="iod-section-tag">{{ sectionTag }}</div>
    <div class="flex-1 flex flex-col justify-center">
      <slot />
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
