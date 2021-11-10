<script setup lang="ts">
import router from '~/router'
</script>

<template>
  <div
    h="screen"
    w="screen"
    display="flex"
    flex="col"
    align="items-center"
    justify="center"
  >
    <div m="b-1" text="3xl" font="bold">404</div>
    <div
      text="blue-500 dark:yellow-400 underline"
      @click="router.push({ path: '/' })"
    >
      Go back
    </div>
  </div>
</template>

<style></style>
