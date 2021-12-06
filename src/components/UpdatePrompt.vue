<script setup lang="ts">
import { useRegisterSW } from 'virtual:pwa-register/vue'
import IconClose from '~icons/mdi/close-thick'

const { offlineReady, needRefresh, updateServiceWorker } = useRegisterSW()

const close = async () => {
  offlineReady.value = false
  needRefresh.value = false
}
</script>

<template>
  <div
    v-if="offlineReady || needRefresh"
    class="pwa-toast"
    role="alert"
    w="full"
    pos="fixed bottom-0"
    p="5"
    bg="light-300 dark:dark-300"
    text="sm black dark:white"
    shadow="~"
  >
    <div class="message" p="b-4" text="center">
      <span v-if="offlineReady"> App funktioniert offline </span>
      <span v-else> Ein neues Update ist verfügbar. </span>
    </div>
    <div display="flex" justify="center">
      <button
        v-if="needRefresh"
        p="y-3 x-7"
        gradient="to-br from-blue-500 to-light-blue-500"
        text="white"
        font="semibold"
        border="rounded"
        shadow="~"
        @click="updateServiceWorker()"
      >
        Aktualisieren
      </button>
      <IconClose @click="close" pos="absolute right-3 top-3" text="gray-400" />
    </div>
  </div>
</template>
