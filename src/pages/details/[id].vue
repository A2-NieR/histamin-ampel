<script setup lang="ts">
import data from '../../data/histamine.json'
import Header from '~/components/Header.vue'

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

let details: Object = {}

if (props.id) {
  for (let i = 0; i < histamine.length; i++) {
    if (histamine[i].list) {
      for (let j = 0; j < histamine[i].list.length; j++) {
        if (histamine[i].list[j].slug === props.id) {
          details = histamine[i].list[j]
        }
      }
    }
  }
}

let bgColor = ''

if (details) {
  if (details.verträglichkeit === 0) {
    bgColor = 'bg-green-500 dark:bg-green-700'
  } else if (details.verträglichkeit === 1) {
    bgColor = 'bg-yellow-500  dark:bg-yellow-600'
  } else if (details.verträglichkeit === 2) {
    bgColor = 'bg-orange-500 dark:bg-orange-700'
  } else if (details.verträglichkeit === 3) {
    bgColor = 'bg-red-500 dark:bg-red-700'
  } else {
    bgColor = 'bg-blue-gray-500 dark:bg-blue-gray-600'
  }
}

let verträglichkeit = ''
if (details.verträglichkeit === 0) {
  verträglichkeit =
    'Gut verträglich. Bei üblicher Verzehrmenge sind keinerlei Symptome zu erwarten.'
} else if (details.verträglichkeit === 1) {
  verträglichkeit =
    'Mäßig verträglich, geringfügige Symptome, gelegentlicher Konsum kleiner Mengen wird oft toleriert.'
} else if (details.verträglichkeit === 2) {
  verträglichkeit =
    'Unverträglich, deutliche Symptome bei üblicher Verzehrsmenge.'
} else if (details.verträglichkeit === 3) {
  verträglichkeit = 'Sehr schlecht verträglich, heftige Symptome.'
} else if (details.verträglichkeit === '?') {
  verträglichkeit = 'Ungenügende oder widersprüchliche Informationen.'
} else {
  verträglichkeit = 'Keine allgemeingültige Aussage möglich.'
}

let histamin = ''
if (details.histamin === 'H!') {
  histamin = 'Hoch Verderblich, rasche Histaminbildung.'
} else if (details.histamin === 'H') {
  histamin = 'Hoher Histamingehalt.'
} else {
  histamin = '-'
}

let amine = ''
if (details.amine === 'A') {
  amine = 'Andere biogene Amine.'
} else {
  amine = '-'
}

let liberator = ''
if (details.liberator === 'L') {
  liberator = 'Liberatoren von Mastzellmediatoren (=Histaminliberatoren).'
} else {
  liberator = '-'
}
let blocker = ''
if (details.blocker === 'B') {
  blocker =
    'Blocker (=Hemmstoffe) der Diaminoxidase oder anderer Histamin abbauender Enzyme.'
} else {
  blocker = '-'
}
</script>

<template>
  <Header :title="details.emoji" />

  <div
    v-if="details"
    display="flex"
    flex="col"
    overflow="scroll"
    h="screen"
    p="t-20"
    :class="bgColor"
    text="white"
  >
    <div p="x-10" display="flex" justify="center" text="lg" font="bold">
      {{ details.name }}
    </div>
    <div display="flex" justify="center">
      <span
        h="38"
        w="38"
        m="y-12"
        bg="white opacity-10"
        border="rounded-full"
        display="flex"
        justify="center"
        align="items-center"
        text="6xl"
        font="bold"
        >{{ details.verträglichkeit }}</span
      >
    </div>

    <div display="flex" flex="col" p="x-10">
      <div m="b-3">{{ verträglichkeit }}</div>
      <div m="b-1"><span font="semibold">Histamin:</span> {{ histamin }}</div>
      <div m="b-1"><span font="semibold">Amine:</span> {{ amine }}</div>
      <div m="b-1"><span font="semibold">Liberator:</span> {{ liberator }}</div>
      <div m="b-1"><span font="semibold">Blocker:</span> {{ blocker }}</div>
      <div m="b-2">
        <span font="semibold">Anmerkungen:</span> {{ details.anmerkungen }}
      </div>
    </div>
  </div>
</template>
