<script setup lang="ts">
import { Icon } from '@iconify/vue'

const socials = [{
  name: 'Github',
  url: 'https://github.com/insulineru',
  icon: 'akar-icons:github-fill',
}, {
  name: 'Twitter',
  url: 'https://twitter.com/insulineru',
  icon: 'akar-icons:twitter-fill',
}, {
  name: 'Telegram',
  url: 'https://facebook.com/insulineru',
  icon: 'bxl:telegram',
}]
</script>

<template>
  <nav class="pt-10 flex justify-between w-full text-base border-t border-t-hex-393C47 max-w-1200px mx-auto">
    <ul class="flex gap-4">
      <li v-for="social in socials" :key="social.name" class="block">
        <a :href="social.url" class="flex items-center justify-center text-white w-10 h-10 rounded-full p-2 bg-hex-272930 hover:bg-hex-393C47 transition-colors" target="_blank" rel="noopener norefferer">
          <Icon width="20px" height="20px" :icon="social.icon" />
        </a>
      </li>
    </ul>
    <p>©2022</p>
    <p>Design by Artem Suslov</p>
  </nav>
</template>
