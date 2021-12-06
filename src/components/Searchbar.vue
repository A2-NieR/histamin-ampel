<script setup lang="ts">
import { computed, ref } from '@vue/reactivity'
// @ts-ignore: Unreachable code error
import router from '~/router'
import data from '../data/histamine.json'

const histamine = [
  ...data.Eier.list,
  ...data.Milchprodukte.list,
  ...data.Fleisch.list,
  ...data.Fisch.list,
  ...data.Meeresfrüchte.list,
  ...data.Diverses.list,
  ...data.Stärkelieferanten.list,
  ...data.Nüsse.list,
  ...data['Fette und Öle'].list,
  ...data.Gemüse.list,
  ...data.Küchenkräuter.list,
  ...data.Früchte.list,
  ...data['Samen, Kerne'].list,
  ...data['Pilze und Algen'].list,
  ...data.Süßungsmittel.list,
  ...data.Gewürze.list,
  ...data.Getränke.list,
  ...data.Alkohol.list,
  ...data.Tee.list,
  ...data['Säfte, Nektare'].list,
  ...data.Koffeingetränke.list,
  ...data.Milchersatz.list,
  ...data['Süßgetränke, Limonaden'].list,
  ...data.Zusatzstoffe.list,
  ...data['Vitamine, Mineralstoffe, Spurenelemente, Stimulantien'].list,
  ...data.Zubereitungen.list
]

const search = ref('')
const result = computed(() => {
  return histamine.filter((item) =>
    item.name.toLowerCase().includes(search.value.toLowerCase())
  )
})

const navTo = (slug: string) => router.push({ path: `/details/${slug}` })
</script>

<template>
  <div display="inline-flex" justify="center" m="y-5 x-7">
    <input
      v-model="search"
      type="text"
      placeholder="Suche..."
      w="full"
      m="t-16"
      p="y-1 x-5"
      bg="light-100 dark:dark-100"
      border="1 solid gray-300 dark:transparent rounded-full"
      shadow="inner"
    />
  </div>
  <div pos="fixed" w="full" display="flex" justify="center" m="t-32">
    <div
      v-if="search"
      h=" max-96"
      w="full"
      m="x-5"
      overflow="auto"
      bg="light-100 dark:dark-300"
      text="black dark:white"
      border="rounded"
      shadow="~"
    >
      <ul text="sm" p="x-5" border="rounded">
        <li
          v-for="item in result"
          p="y-5"
          border="b-1 solid gray-300 dark:gray-400"
          @click="navTo(item.slug)"
        >
          {{ item.emoji }} {{ item.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
