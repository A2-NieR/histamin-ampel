<script setup lang="ts">
const props = defineProps({
  title: String
})
</script>

<template>
  <div
    h="15"
    display="flex"
    align="items-center"
    justify="center"
    shadow="~"
    font="bold"
  >
    {{ props.title }}
  </div>
</template>
