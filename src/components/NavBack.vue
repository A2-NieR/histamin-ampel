<script setup lang="ts">
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
