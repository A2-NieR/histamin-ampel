<script setup lang="ts">
const props = defineProps({
  cardName: String,
  emoji: String
})
</script>

<template>
  <div
    h="22"
    w="22"
    m="2"
    p="2"
    display="flex"
    flex="col"
    align="items-center"
    justify="center"
    border="1 solid gray-200 dark:light-300 rounded-md "
    shadow="~"
  >
    <div m="b-1">{{ props.emoji }}</div>
    <div text="xs break-word center">{{ props.cardName }}</div>
  </div>
</template>
