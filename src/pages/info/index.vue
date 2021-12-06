<script setup lang="ts">
import { ref } from 'vue'
// @ts-ignore: Unreachable code error
import router from '~/router'
import Header from '~/components/Header.vue'
import IconDocument from '~icons/mdi/file-document'
import IconInstall from '~icons/mdi/cellphone-arrow-down'
import IconCoffeeFill from '~icons/mdi/coffee'
import IconCoffeeOut from '~icons/mdi/coffee-outline'
import IconClose from '~icons/mdi/close-thick'

const modalOpen = ref(false)

const goTo = (link: string) => router.push(link)
</script>

<template>
  <div>
    <Header title="📄 Info" />

    <div
      h="screen"
      z="30"
      display="flex"
      flex="col"
      overflow="scroll"
      p="t-22 x-7"
    >
      <div display="flex" flex="col" border="rounded" shadow="lg">
        <div m="b-3">
          Hier können Sie Hinweise und Erläuterungen zur App, sowie den
          einzelnen Fachbegriffen und Skalen nachschlagen.
        </div>
        <!-- Info -->
        <div
          @click="goTo('/info/about')"
          display="flex"
          align="items-center"
          border="1 solid b-transparent rounded-t"
        >
          <IconDocument m="x-5" />
          <div p="y-5">Hinweise & Erläuterungen</div>
        </div>

        <!-- Installation -->
        <div
          @click="goTo('/info/about')"
          display="flex"
          align="items-center"
          border="1 solid rounded-b"
        >
          <IconInstall m="x-5" />
          <div p="y-5">Installation als App</div>
        </div>

        <div m="y-3">
          Wenn Ihnen die App einen Mehrwert bietet, können Sie dem Entwickler
          gerne einen Kaffee spendieren. Dies ist jedoch freiwillig, auch ohne
          können Sie die App selbstverständlich in vollem Umfang nutzen.
        </div>

        <!-- Fiat -->
        <div
          @click="modalOpen = !modalOpen"
          display="flex"
          align="items-center"
          border="1 solid b-transparent rounded-t"
        >
          <IconCoffeeFill m="x-5" />
          <div p="y-5">Kaffeekasse</div>
        </div>

        <!-- Krypto -->
        <div
          @click="goTo('/info/crypto')"
          display="flex"
          align="items-center"
          border="1 solid gray-300 rounded-b"
        >
          <IconCoffeeOut m="x-5" />
          <div p="y-5">Kaffeekasse (Krypto)</div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <teleport to="body">
      <div
        v-if="modalOpen"
        h="full"
        w="full"
        z="50"
        pos="absolute top-0"
        display="flex"
        flex="col"
        align="items-center"
        justify="center"
        bg="black opacity-50"
      >
        <IconClose
          @click="modalOpen = !modalOpen"
          h="6"
          w="6"
          pos="absolute top-6 right-6"
        />
        <iframe
          h="screen"
          id="kofiframe"
          src="https://ko-fi.com/imugi/?hidefeed=true&widget=true&embed=true&preview=true"
          style="border: none; width: 100%; padding: 4px; background: #f9f9f9"
          height="712"
          title="imugi"
        ></iframe>
      </div>
    </teleport>
  </div>
</template>
