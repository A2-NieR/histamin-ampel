<script setup lang="ts">
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
  </div>
</template>
