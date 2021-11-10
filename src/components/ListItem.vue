<script setup lang="ts">
const props = defineProps({
  item: Object
})

let bgColor = ''
let txtColor = ''
let mainTxtColor = ''

if (props.item) {
  if (props.item.verträglichkeit === 0) {
    bgColor =
      'bg-gradient-to-b from-green-500 to-lime-500 dark:from-green-600 dark:to-lime-600'
    txtColor = 'text-green-500 dark:text-green-600'
    mainTxtColor = 'white'
  } else if (props.item.verträglichkeit === 1) {
    bgColor =
      'bg-gradient-to-b from-yellow-400 to-yellow-300 dark:from-yellow-500 dark:to-yellow-400'
    txtColor = 'text-yellow-400 dark:text-yellow-500'
    mainTxtColor = 'black'
  } else if (props.item.verträglichkeit === 2) {
    bgColor =
      'bg-gradient-to-b from-orange-500 to-amber-500 dark:from-orange-600 dark:to-amber-600'
    txtColor = 'text-orange-500 dark:text-orange-700'
    mainTxtColor = 'white'
  } else if (props.item.verträglichkeit === 3) {
    bgColor =
      'bg-gradient-to-b from-red-600 to-orange-600 dark:from-red-700 dark:to-orange-700'
    txtColor = 'text-red-500 dark:text-red-700'
    mainTxtColor = 'white'
  } else {
    bgColor =
      'bg-gradient-to-b from-blue-gray-500 to-gray-400 dark:from-blue-gray-600 dark:to-gray-500'
    txtColor = 'text-blue-gray-500 dark:text-blue-gray-600'
    mainTxtColor = 'white'
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
    font="semibold"
  >
    <span>{{ item.emoji }}</span>
    <span p="l-3 r-8" :text="mainTxtColor">{{ item.name }}</span>
    <span
      pos="absolute right-3"
      display="flex"
      align="items-center"
      justify="center"
      h="8"
      w="8"
      border="rounded-full"
      bg="white"
      font="semibold"
      shadow="inner"
      :class="`${txtColor}`"
      >{{ item.verträglichkeit }}</span
    >
  </div>
</template>
