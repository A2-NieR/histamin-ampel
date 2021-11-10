<script setup lang="ts">
const props = defineProps({
  item: Object
})
let bgColor = ''
let txtColor = ''

if (props.item) {
  if (props.item.verträglichkeit === 0) {
    bgColor = 'bg-green-500 dark:bg-green-700'
    txtColor = 'text-green-500 dark:text-green-700'
  } else if (props.item.verträglichkeit === 1) {
    bgColor = 'bg-yellow-500 dark:bg-yellow-600'
    txtColor = 'text-yellow-500 dark:text-yellow-600'
  } else if (props.item.verträglichkeit === 2) {
    bgColor = 'bg-orange-500 dark:bg-orange-700'
    txtColor = 'text-orange-500 dark:text-orange-700'
  } else if (props.item.verträglichkeit === 3) {
    bgColor = 'bg-red-500 dark:bg-red-700'
    txtColor = 'text-red-500 dark:text-red-700'
  } else {
    bgColor = 'bg-blue-gray-500 dark:bg-blue-gray-600'
    txtColor = 'text-blue-gray-500 dark:text-blue-gray-600'
  }
}
</script>

<template>
  <div
    v-if="item"
    :class="`${bgColor}`"
    pos="relative"
    display="flex"
    flex="row"
    justify=" start"
    align="items-center"
    h="22"
    m="y-1 x-5"
    p="y-3 l-3 r-4"
    border="rounded"
    shadow="~"
    text="white"
    font="semibold"
  >
    <span>{{ item.emoji }}</span>
    <span p="l-3 r-8">{{ item.name }}</span>
    <span
      pos="absolute right-3"
      display="flex"
      align="items-center"
      justify="center"
      h="8"
      w="8"
      border="rounded-full"
      bg="white"
      font="bold"
      shadow="inner"
      :class="`${txtColor}`"
      >{{ item.verträglichkeit }}</span
    >
  </div>
</template>
