<script lang="ts" setup>
defineProps<{ position: 'left' | 'right' }>()
</script>

<template>
  <aside class="absolute h-36 w-100vh rotate-90 origin-bottom top-64" :class="position === 'right' ? '-right-64' : '-left-64'">
    <slot />
  </aside>
</template>
