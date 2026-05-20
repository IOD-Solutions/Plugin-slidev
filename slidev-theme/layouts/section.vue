<script setup lang="ts">
const props = defineProps<{
  num?: string | number
}>()

// Only zero-pad numeric values. Letters or words ("A", "B", "Annexes")
// render as-is so `num: B` produces "B", not "0B".
const display = () => {
  if (props.num === undefined || props.num === null) return undefined
  if (typeof props.num === 'number') return String(props.num).padStart(2, '0')
  const s = String(props.num)
  return /^\d+$/.test(s) ? s.padStart(2, '0') : s
}
</script>

<template>
  <div class="slidev-layout iod-layout-section">
    <div v-if="display() !== undefined" class="section-number">
      {{ display() }}
    </div>
    <slot />
  </div>
</template>
