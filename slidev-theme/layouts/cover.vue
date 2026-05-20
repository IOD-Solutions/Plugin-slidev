<script setup lang="ts">
import logoUrl from '../assets/iod-logo.png'
</script>

<template>
  <div class="slidev-layout iod-layout-cover">
    <slot />
    <img :src="logoUrl" alt="IoD solutions" class="iod-cover-logo" />
  </div>
</template>
