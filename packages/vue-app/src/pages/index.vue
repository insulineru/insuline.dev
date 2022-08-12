<script setup lang="ts">
import cryptoIcon from '~/assets/images/crypto.svg'
import wellnessIcon from '~/assets/images/wellness.svg'
import weedIcon from '~/assets/images/weed.svg'
const info = [{
  title: 'Wellness',
  img: wellnessIcon,
}, {
  title: 'Crypto',
  img: cryptoIcon,
}, {
  title: 'Entertainment',
  img: weedIcon,
}]
</script>

<template>
  <main class="h-full w-full flex flex-col justify-between max-w-1200px mx-auto">
    <h1 class="text-113px leading-none font-medium mt-22">
      <img src="../assets/images/hand.svg" alt="👋" width="100" height="100" class="inline-block -mt-8">
      I'm Insuline, <br> a web 3.0 developer
    </h1>
    <TheTicker duration="30s">
      <div v-for="{ title, img } in info" :key="title" class="inline-flex items-center">
        <span class="text-72px leading-none uppercase">{{ title }}</span>
        <img :src="img" class="w-auto h-20 mx-8" :alt="title">
      </div>
    </TheTicker>
  </main>
</template>
