<script setup lang="ts">
const route = useRoute()
const isMainPage = computed(() => route.fullPath === '/')
</script>

<template>
  <header class="flex w-full max-w-1200px mx-auto justify-between items-center mt-6" :class="isMainPage ? 'pr-32' : 'pl-32'">
    <img src="../assets/images/logo.svg" alt="Logo" width="69" height="11">
    <button class="px-6 py-4 bg-hex-E7E9EE hover:bg-hex-36BF54 font-medium transition-colors rounded-52px text-hex-0D0F13 leading-5 mr-2 cursor-pointer">
      Connect wallet
    </button>
  </header>
</template>
