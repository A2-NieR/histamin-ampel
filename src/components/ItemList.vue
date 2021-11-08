<script setup lang="ts">
import router from '~/router'
import ItemCard from './ItemCard.vue'
</script>

<template>
  <div h="full" p="x-5" display="flex" flex="col" overflow="auto">
    <div display="inline-flex" justify="center" text="lg" font="semibold">
      Tierisch
    </div>
    <div
      p="t-3 b-5"
      display="flex"
      flex="wrap"
      align="items-center"
      justify="evenly"
    >
      <ItemCard
        :emoji="'🥚'"
        :cardName="'Eier'"
        @click="router.push({ path: '/0' })"
      />
      <ItemCard
        :emoji="'🥛'"
        :cardName="'Milch-produkte'"
        @click="router.push({ path: '/1' })"
      />
      <ItemCard
        :emoji="'🥩'"
        :cardName="'Fleisch'"
        @click="router.push({ path: '/2' })"
      />
      <ItemCard
        :emoji="'🐟'"
        :cardName="'Fisch'"
        @click="router.push({ path: '/3' })"
      />
      <ItemCard
        :emoji="'🍤'"
        :cardName="'Meeres-früchte'"
        @click="router.push({ path: '/4' })"
      />
      <ItemCard
        :emoji="'🥫'"
        :cardName="'Diverses'"
        @click="router.push({ path: '/5' })"
      />
    </div>

    <div display="inline-flex" justify="center" text="lg" font="semibold">
      Pflanzlich
    </div>
    <div
      p="t-3 b-5"
      display="flex"
      flex="wrap"
      align="items-center"
      justify="evenly"
    >
      <ItemCard
        :emoji="'🍞'"
        :cardName="'Stärke-lieferanten'"
        @click="router.push({ path: '/6' })"
      />
      <ItemCard
        :emoji="'🥜'"
        :cardName="'Nüsse'"
        @click="router.push({ path: '/7' })"
      />
      <ItemCard
        :emoji="'🧈'"
        :cardName="'Fette & Öle'"
        @click="router.push({ path: '/8' })"
      />
      <ItemCard
        :emoji="'🥕'"
        :cardName="'Gemüse'"
        @click="router.push({ path: '/9' })"
      />
      <ItemCard
        :emoji="'🌿'"
        :cardName="'Küchen-kräuter'"
        @click="router.push({ path: '/10' })"
      />
      <ItemCard
        :emoji="'🍎'"
        :cardName="'Früchte'"
        @click="router.push({ path: '/11' })"
      />
      <ItemCard
        :emoji="'🌻'"
        :cardName="'Samen & Kerne'"
        @click="router.push({ path: '/12' })"
      />
      <ItemCard
        :emoji="'🍄'"
        :cardName="'Pilze & Algen'"
        @click="router.push({ path: '/13' })"
      />
      <ItemCard
        :emoji="'🍯'"
        :cardName="'Süßungs-mittel'"
        @click="router.push({ path: '/14' })"
      />
      <ItemCard
        :emoji="'🧂'"
        :cardName="'Gewürze'"
        @click="router.push({ path: '/15' })"
      />
      <ItemCard
        :emoji="'🥤'"
        :cardName="'Getränke'"
        @click="router.push({ path: '/16' })"
      />
      <ItemCard
        :emoji="'🍺'"
        :cardName="'Alkohol'"
        @click="router.push({ path: '/17' })"
      />
      <ItemCard
        :emoji="'🍵'"
        :cardName="'Tee'"
        @click="router.push({ path: '/18' })"
      />
      <ItemCard
        :emoji="'🧃'"
        :cardName="'Säfte & Nektare'"
        @click="router.push({ path: '/19' })"
      />
      <ItemCard
        :emoji="'☕'"
        :cardName="'Koffein-getränke'"
        @click="router.push({ path: '/20' })"
      />
      <ItemCard
        :emoji="'🥛'"
        :cardName="'Milchersatz'"
        @click="router.push({ path: '/21' })"
      />
      <ItemCard
        :emoji="'🍹'"
        :cardName="'Süßgetränke / Limonaden'"
        @click="router.push({ path: '/22' })"
      />
      <ItemCard
        :emoji="'🧪'"
        :cardName="'Zusatzstoffe'"
        @click="router.push({ path: '/23' })"
      />
      <ItemCard
        :emoji="'❤'"
        :cardName="'Vitamine, Mineralstoffe, etc.'"
        @click="router.push({ path: '/24' })"
      />
      <ItemCard
        :emoji="'🍫'"
        :cardName="'Zubereitungen'"
        @click="router.push({ path: '/25' })"
      />
    </div>
  </div>
</template>
