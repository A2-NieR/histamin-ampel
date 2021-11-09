<script setup lang="ts">
import router from '~/router'
import data from '../data/histamine.json'
import ListItem from '~/components/ListItem.vue'
import NavBack from '~/components/NavBack.vue'

const props = defineProps({
  id: String
})

const histamine = [
  data.Eier,
  data.Milchprodukte,
  data.Fleisch,
  data.Fisch,
  data.Meeresfrüchte,
  data.Diverses,
  data.Stärkelieferanten,
  data.Nüsse,
  data['Fette und Öle'],
  data.Gemüse,
  data.Küchenkräuter,
  data.Früchte,
  data['Samen, Kerne'],
  data['Pilze und Algen'],
  data.Süßungsmittel,
  data.Gewürze,
  data.Getränke,
  data.Alkohol,
  data.Tee,
  data['Säfte, Nektare'],
  data.Koffeingetränke,
  data.Milchersatz,
  data['Süßgetränke, Limonaden'],
  data.Zusatzstoffe,
  data['Vitamine, Mineralstoffe, Spurenelemente, Stimulantien'],
  data.Zubereitungen
]

//TODO: Filter by verträglichkeit w/ checkbox
</script>

<template>
  <div bg="light-300 dark:dark-300" text="dark-900 dark:light-100">
    <div
      h="18"
      w="full"
      z="50"
      pos="fixed"
      display="flex"
      align="items-center"
      justify="center"
      bg="light-100 dark:dark-300"
      shadow="~"
    >
      <NavBack />
      <span font="bold">{{ histamine[parseInt(props.id)].name }}</span>
    </div>
    <ul
      v-if="props.id"
      h="screen"
      display="flex"
      flex="col"
      overflow=" scroll"
      p="t-20"
    >
      <li v-for="item in histamine[parseInt(props.id)].list">
        <ListItem
          @click="router.push({ path: `/details/${item.slug}` })"
          :item="item"
          :level="item.verträglichkeit"
        />
      </li>
    </ul>
  </div>
</template>

<style></style>
