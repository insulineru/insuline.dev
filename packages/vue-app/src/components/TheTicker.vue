<script setup lang="ts">
defineProps<{
  duration: string
}>()
</script>

<template>
  <div class="ticker-wrapper">
    <div class="ticker">
      <slot />
    </div>
  </div>
</template>

<style>
@-webkit-keyframes ticker {
  0% {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    visibility: visible;
  }

  100% {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
  }
}

@keyframes ticker {
  0% {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    visibility: visible;
  }

  100% {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
  }
}

.ticker-wrapper {
  width: 100%;
  padding-left: 100%;
  overflow-x: hidden;
  height: 122px;
  border-top: 1px solid white;
  border-bottom: 1px solid white;
}

.ticker {
  display: inline-block;
  height: 4rem;
  padding-top: 24px;
  line-height: 4rem;
  white-space: nowrap;
  padding-right: 100%;
  box-sizing: content-box;

  animation-iteration-count: infinite;
  animation-timing-function: linear;
  animation-name: ticker;
  animation-duration: v-bind(duration);
}
</style>
