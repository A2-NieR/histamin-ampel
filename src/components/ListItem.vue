<script setup lang="ts">
const props = defineProps({
  item: Object
})
let bgColor = ''
let txtColor = ''

if (props.item) {
  if (props.item.verträglichkeit === 0) {
    bgColor = 'bg-green-500'
    txtColor = 'text-green-500'
  } else if (props.item.verträglichkeit === 1) {
    bgColor = 'bg-yellow-500'
    txtColor = 'text-yellow-500'
  } else if (props.item.verträglichkeit === 2) {
    bgColor = 'bg-orange-500'
    txtColor = 'text-orange-500'
  } else if (props.item.verträglichkeit === 3) {
    bgColor = 'bg-red-500'
    txtColor = 'text-red-500'
  } else {
    bgColor = 'bg-blue-gray-500'
    txtColor = 'text-blue-gray-500'
  }
}
</script>

<template>
  <div
    v-if="item"
    :class="`${bgColor}`"
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
      pos="absolute right-8"
      display="flex"
      align="items-center"
      justify="center"
      h="8"
      w="8"
      border="rounded-full"
      bg="white"
      font="bold"
      :class="`${txtColor}`"
      >{{ item.verträglichkeit }}</span
    >
  </div>
</template>
