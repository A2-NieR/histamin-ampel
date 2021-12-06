<script setup lang="ts">
// @ts-ignore: Unreachable code error
import router from '~/router'
import IconFilter from '~icons/mdi/filter'
import IconInfo from '~icons/mdi/information'

const goTo = (link: string) => router.push(link)
</script>

<template>
  <div
    h="16"
    w="full"
    z="40"
    pos="fixed bottom-0"
    display="flex"
    align="items-center"
    justify="around"
    bg="light-100 dark:dark-200"
    text="blue-gray-500 dark:light-100"
    shadow="~"
  >
    <div
      display="flex"
      flex="col"
      align="items-center"
      justify="center"
      text="gray-600"
    >
      <IconFilter />
      <span text="xs">Filter</span>
    </div>
    <div
      @click="goTo('info')"
      display="flex"
      flex="col"
      align="items-center"
      justify="center"
    >
      <IconInfo />
      <span text="xs">Info</span>
    </div>
  </div>
</template>
