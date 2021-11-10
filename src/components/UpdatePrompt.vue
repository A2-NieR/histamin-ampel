<script setup lang="ts">
import { useRegisterSW } from 'virtual:pwa-register/vue'

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
    pos="fixed bottom-0"
    p="3"
    bg="light-100 dark:300"
    text="current dark:white"
    shadow="~"
  >
    <div class="message" p="b-3">
      <span v-if="offlineReady"> App funktioniert offline </span>
      <span v-else>
        Ein neues Update ist verfügbar. Zum Aktualisieren bitte auf Update
        klicken.
      </span>
    </div>
    <div display="flex" justify="center">
      <button
        v-if="needRefresh"
        m="r-2"
        p="y-1 x-3"
        gradient="to-br from-blue-500 to-blue-400"
        text="white"
        border="rounded"
        @click="updateServiceWorker()"
      >
        Update
      </button>
      <button
        m="r-1"
        p="y-1 x-3"
        gradient="to-br from-gray-400 to-gray-300"
        text="white"
        border="rounded"
        @click="close"
      >
        Abbrechen
      </button>
    </div>
  </div>
</template>
