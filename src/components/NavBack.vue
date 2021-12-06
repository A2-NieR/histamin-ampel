<script setup lang="ts">
// @ts-ignore: Unreachable code error
import router from '~/router'
import IconBack from '~icons/mdi/arrow-left'
</script>

<template>
  <IconBack
    pos="absolute left-5"
    text="black dark:white"
    @click="router.go(-1)"
  />
</template>
