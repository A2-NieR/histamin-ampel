<script setup lang="ts">
import router from '~/router'
import InfoIcon from '~icons/mdi/information'
import NavBack from './NavBack.vue'
const props = defineProps({
  title: String
})
</script>

<template>
  <div
    h="16"
    w="full"
    z="50"
    pos="fixed"
    display="flex"
    align="items-center"
    justify="center"
    bg="light-100 dark:dark-200"
    shadow="~"
    font="bold"
  >
    <NavBack v-if="props.title !== 'Histamin Ampel 🚥'" />
    {{ props.title }}
    <InfoIcon
      v-if="props.title === 'Histamin Ampel 🚥'"
      h="6"
      w="6"
      pos="absolute right-5"
      text="blue-500 dark:light-blue-500"
      @click="router.push({ path: '/info' })"
    />
  </div>
</template>
