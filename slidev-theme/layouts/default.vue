<script setup lang="ts">
import logoUrl from '../assets/iod-logo.png'

defineProps<{
  meta?: string
  sectionTag?: string
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-default">
    <div v-if="sectionTag" class="iod-section-tag">{{ sectionTag }}</div>
    <div class="iod-content">
      <slot />
    </div>
    <footer class="iod-footer">
      <img :src="logoUrl" alt="IoD solutions" class="logo" />
      <div class="meta">
        <span v-if="meta">{{ meta }}</span>
        <span v-if="meta" class="divider">—</span>
        <span><SlideCurrentNo /> / <SlidesTotal /></span>
      </div>
    </footer>
  </div>
</template>
