<script setup lang="ts">
import { Clipboard } from '@capacitor/clipboard'
import Header from '~/components/Header.vue'
import IconBTC from '~icons/logos/bitcoin'
import IconXMR from '~icons/logos/monero'

const btc = '3BnACE12pz4GpPrUq5PzTdBa4HTqQorN9s'
const xmr =
  '8ApdbcAJ4Uw1cy34Xsor5F8giTBXD1yasUj1wgwpoWugAS2F5sVpXDJT9EdzwaApM6VtBuNqmq981iQsorD7w7uVK1qwbNk'

const btcToClipboard = async () => {
  await Clipboard.write({
    string: btc
  })
}

const xmrToClipboard = async () => {
  await Clipboard.write({
    string: xmr
  })
}
</script>

<template>
  <div>
    <Header title="☕ Kaffeekasse (Krypto)" />
    <div
      h="screen"
      z="30"
      display="flex"
      flex="col"
      overflow="scroll"
      p="t-22 x-7"
    >
      <div text="center">
        Sie können den Entwickler auch mithilfe von folgenden Kryptowährungen
        unterstützen:
      </div>

      <!-- BTC -->
      <div
        m="t-8"
        display="flex"
        flex="col"
        align="items-center"
        justify="center"
      >
        <IconBTC h="16" w="16" />
        <div m="t-3" font="semibold">Bitcoin Adresse:</div>
        <code
          w="6/7"
          m="t-2"
          p="2"
          border="1 solid gray-300 rounded"
          text="center break-words"
          >{{ btc }}</code
        >
        <button
          @click="btcToClipboard"
          m="t-3"
          p="y-3 x-7"
          gradient="to-br from-blue-500 to-light-blue-500"
          text="white"
          font="semibold"
          border="rounded"
          shadow="~"
        >
          Bitcoin Adresse kopieren
        </button>
      </div>

      <!-- XMR -->
      <div
        m="t-8"
        display="flex"
        flex="col"
        align="items-center"
        justify="center"
      >
        <IconXMR h="16" w="16" />
        <div m="t-3" font="semibold">Monero Adresse:</div>
        <code
          w="6/7"
          m="t-2"
          p="2"
          border="1 solid gray-300 rounded"
          text="center break-words"
          >{{ xmr }}</code
        >
        <button
          @click="xmrToClipboard"
          m="t-3"
          p="y-3 x-7"
          gradient="to-br from-blue-500 to-light-blue-500"
          text="white"
          font="semibold"
          border="rounded"
          shadow="~"
        >
          Monero Adresse kopieren
        </button>
      </div>
    </div>
  </div>
</template>
