<script setup lang="ts">
import router from '~/router'
import IconBack from '~icons/mdi/arrow-left'

const navBack = () => router.go(-1)
</script>

<template>
  <IconBack pos="absolute left-5" @click="navBack" />
</template>
