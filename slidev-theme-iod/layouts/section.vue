<script setup lang="ts">
defineProps<{
  num?: string | number
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-section">
    <div v-if="num !== undefined" class="section-number">
      {{ String(num).padStart(2, '0') }}
    </div>
    <slot />
  </div>
</template>
