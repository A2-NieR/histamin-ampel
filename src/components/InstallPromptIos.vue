<script setup lang="ts">
import IconShare from '~icons/ic/baseline-ios-share'
import IconAdd from '~icons/ic/outline-add-box'
import { ref } from '@vue/reactivity'

const showIosInstall = ref(false)

const isIos = () => {
  const userAgent = window.navigator.userAgent.toLowerCase()
  return /iphone|ipad|ipod/.test(userAgent)
}

const isInStandaloneMode = () =>
  'standalone' in window.navigator && window.navigator.standalone

if (isIos() && !isInStandaloneMode()) {
  showIosInstall.value = true
}
</script>

<template>
  <div
    v-if="showIosInstall"
    class="ios-toast"
    role="alert"
    w="full"
    pos="fixed bottom-0"
    p="5"
    bg="light-100 dark:dark-300"
    text="current dark:white"
    shadow="~"
  >
    <div class="message" display="flex" align="items-center" p="b-3">
      <span text="sm">
        Zum Installieren als App in Safari auf
        <IconShare h="5" w="5" m="x-1" text="blue-500 dark:light-blue-500" />
        tippen und anschließend zum Startbildschirm hinzufügen
        <IconAdd h="6" w="6" text="black dark:white middle" />
      </span>
    </div>
  </div>
</template>
