<script setup lang="ts">
import { Icon } from '@iconify/vue'
const router = useRouter()

const name = $ref('')
const isDisabled = computed(() => name.length === 0)
</script>

<template>
  <main class="h-full w-full flex items-center justify-center max-w-1200px mx-auto pl-32">
    <div class="flex justify-between items-center">
      <div>
        <h1 class="text-80px leading-none font-medium mt-22">
          Do you want .insuline ENS?
        </h1>
        <p>ENS helps you translate complex identifiers in Web3 into readable names, which are then registered in the Ethereum blockchain.</p>
        <form class="flex items-center justify-between p-4 bg-hex-191A1F rounded-92px mt-14 border-hex-393C47 border">
          <div class="flex items-center gap-2 ml-4">
            <input v-model="name" v-autowidth type="text" placeholder="Enter your name" class="bg-transparent placeholder:color-hex-424652 color-white text-2xl py-2 outline-none" maxlength="16" pattern="[a-zA-Z0-9]+">
            <span class="px-4 py-1 rounded-xl text-2xl bg-hex-272930">.insuline</span>
          </div>
          <button type="submit" class="text-base py-6 px-10 text-base bg-hex-4ACC67 rounded-57px uppercase text-hex-111318 transition-opacity" :class="isDisabled && 'opacity-30 pointer-events-none cursor-disabled'">
            Mint
          </button>
        </form>
      </div>
      <div class="border border-hex-272930 rounded-xl p-4 pb-6.5 text-2xl text-white ml-36">
        <TheNft width="270" class="bg-hex-111318 border border-hex-272930 mb-8 rounded-md" :name="name" />
        <p class="mb-4 flex items-center gap-1">
          <span :class="!name && 'text-hex-393C47'">
            {{ name ? name : 'Your name' }}
          </span>
          <span>.insuline</span>
        </p>
        <p class="flex items-center font-medium gap-1">
          <span class="leading-none">0.0228</span>
          <img src="../assets/images/eth.svg" alt="Ethereum" width="23" height="23">
        </p>
      </div>
    </div>
  </main>
  <BaseAside position="left" class="bg-hex-191A1F flex items-center justify-center">
    <span class="text-white text-28px leading-35px mr-6">main</span>
    <button class="w-16 h-16 flex items-center justify-center border-1.5px rounded-full border-hex-white hover:bg-hex-36BF54 transition-colors" @click="router.push('/')">
      <Icon icon="bi:arrow-down" class="text-white font-bold" width="28px" height="18px" />
    </button>
  </BaseAside>
</template>
