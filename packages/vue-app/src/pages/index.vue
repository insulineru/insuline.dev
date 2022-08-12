<script setup lang="ts">
import { Icon } from '@iconify/vue'
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

const isScammed = $ref(false)
</script>

<template>
  <main class="h-full w-full flex flex-col justify-between max-w-1200px mx-auto pr-32">
    <h1 class="text-70px md:text-113px leading-none font-medium mt-22">
      <img src="../assets/images/hand.svg" alt="👋" width="100" height="100" class="inline-block -mt-8">
      {{ !isScammed ? `I'm Insuline, a&nbsp;web&nbsp;3.0 developer` : 'Тебя заскамили, дружище 🤡' }}
    </h1>
    <TheTicker duration="30s">
      <div v-for="{ title, img } in info" :key="title" class="inline-flex items-center">
        <span class="text-72px leading-none uppercase">{{ title }}</span>
        <img :src="img" class="w-auto h-20 mx-8" :alt="title">
      </div>
    </TheTicker>
  </main>
  <BaseAside position="right" class="bg-hex-4ACC67 flex items-center justify-center">
    <span class="mr-4 text-2xl pt-1 pb-2 pl-3 pr-4 text-hex-272930 bg-hex-64D37C rounded-xl">.insuline</span>
    <span class="text-hex-111318 text-28px leading-35px mr-6">ENS domain</span>
    <button class="w-16 h-16 flex items-center justify-center border-1.5px rounded-full border-hex-111318 hover:bg-hex-36BF54 transition-colors" @click="isScammed = !isScammed">
      <Icon icon="bi:arrow-down" class="-rotate-180 text-hex-111318 font-bold" width="28px" height="18px" />
    </button>
  </BaseAside>
</template>
