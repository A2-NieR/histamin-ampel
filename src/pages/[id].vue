<script setup lang="ts">
import data from '../data/histamine.json'
import ListItem from '~/components/ListItem.vue'
import NavBack from '~/components/NavBack.vue'
import Footer from '~/components/Footer.vue'

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
</script>

<template>
  <div h="full" bg="light-300 dark:dark-300" text="dark-900 dark:light-100">
    <div
      h="12"
      w="full"
      z="50"
      pos="fixed"
      display="flex"
      align="items-center"
      justify="center"
      bg="light-300 dark:dark-300"
      shadow="~"
    >
      <NavBack />
      <span font="bold">{{ histamine[parseInt(props.id)].name }}</span>
    </div>
    <ul v-if="props.id" display="flex" flex="col" h="full" p="y-14">
      <li v-for="item in histamine[parseInt(props.id)].list">
        <ListItem :item="item" :level="item.verträglichkeit" />
      </li>
    </ul>

    <!-- <Footer /> -->
  </div>
</template>

<style></style>
