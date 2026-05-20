<script setup lang="ts">
import logoUrl from '../assets/iod-logo.png'

defineProps<{
  email?: string
  phone?: string
  website?: string
  linkedin?: string
}>()
</script>

<template>
  <div class="slidev-layout iod-layout-end">
    <h1>Merci !</h1>
    <div class="question">Vous avez des questions ?</div>
    <div v-if="email || phone || website || linkedin" class="contacts">
      <div v-if="email">{{ email }}</div>
      <div v-if="phone">{{ phone }}</div>
      <div v-if="website"><a :href="`https://${website}`">{{ website }}</a></div>
      <div v-if="linkedin">{{ linkedin }}</div>
    </div>
    <slot />
    <img :src="logoUrl" alt="IoD solutions" class="end-logo" />
  </div>
</template>
