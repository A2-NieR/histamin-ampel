<script setup lang="ts">
import router from '~/router'
import InfoIcon from '~icons/mdi/information'
const props = defineProps({
  title: String
})
</script>

<template>
  <div
    h="18"
    display="flex"
    align="items-center"
    justify="center"
    bg="light-100 dark:dark-200"
    shadow="~"
    font="bold"
  >
    {{ props.title }}
    <InfoIcon
      h="6"
      w="6"
      pos="absolute right-5"
      text="blue-500 dark:yellow-400"
      @click="router.push({ path: '/info' })"
    />
  </div>
</template>
