<script setup lang="ts">
import Header from '~/components/Header.vue'
</script>

<template>
  <div>
    <Header title="ℹ️ Hinweise" />

    <div
      h="screen"
      display="flex"
      flex="col"
      overflow="scroll"
      p="t-22 x-5 b-5"
    >
      <span display="inline-flex" justify="center" p="b-3" text="lg" font="bold"
        >Histamin-Ampel</span
      >
      <span p="b-3"
        >Die Histamin-Ampel dient als digitales Nachschlagewerk und basiert auf
        der Verträglichkeitsliste für die diagnostische und therapeutische
        Auslassdiät bei Histaminose (Mastzellaktivitätssyndrom MCAS,
        Mastozytose, Histamin-Intoleranz), der Websites
        <a
          class="text-blue-500 dark:text-yellow-400 underline"
          href="http://www.mastzellaktivierung.info"
          >mastzellaktivierung.info</a
        >
        und
        <a
          class="text-blue-500 dark:text-yellow-400 underline"
          href="http://www.histaminintoleranz.ch"
          >histaminintoleranz.ch</a
        >.</span
      >

      <span
        display="inline-flex"
        justify="center"
        p="t-5 b-3"
        text="lg"
        font="semibold"
        >Verträglichkeitsskala</span
      >
      <span p="b-1" font="semibold">Histamin:</span>
      <span
        m="b-1"
        p="y-2 x-3"
        class="
          bg-gradient-to-b
          from-green-500
          to-lime-500
          dark:from-green-600 dark:to-lime-600
        "
        text="white"
        border="rounded"
        font="semibold"
        >0: Gut verträglich. Bei üblicher Verzehrmenge sind keinerlei Symptome
        zu erwarten.</span
      >
      <span
        m="b-1"
        p="y-2 x-3"
        class="
          bg-gradient-to-b
          from-yellow-400
          to-yellow-300
          dark:from-yellow-500 dark:to-yellow-400
        "
        text="black"
        border="rounded"
        font="semibold"
        >1: Mäßig verträglich, geringfügige Symptome, gelegentlicher Konsum
        kleiner Mengen wird oft toleriert</span
      >
      <span
        m="b-1"
        p="y-2 x-3"
        class="
          bg-gradient-to-b
          from-orange-500
          to-amber-500
          dark:from-orange-600 dark:to-amber-600
        "
        text="white"
        border="rounded"
        font="semibold"
        >2: Unverträglich, deutliche Symptome bei üblicher Verzehrmenge.</span
      >
      <span
        m="b-1"
        p="y-2 x-3"
        class="
          bg-gradient-to-b
          from-red-600
          to-orange-600
          dark:from-red-700 dark:to-orange-700
        "
        text="white"
        border="rounded"
        font="semibold"
        >3: Sehr schlecht verträglich, heftige Symptome.</span
      >
      <span m="b-1" p="y-2 x-3" font="semibold"
        >- : Keine allgemeingültige Aussage möglich.</span
      >
      <span
        m="b-5"
        p="y-2 x-3"
        class="
          bg-gradient-to-b
          from-blue-gray-500
          to-gray-400
          dark:from-blue-gray-600 dark:to-gray-500
        "
        text="white"
        border="rounded"
        font="semibold"
        >?: Ungenügende oder widersprüchliche Informationen,</span
      >
      <span p="b-3"
        >Die Angaben gelten immer nur für das reine Lebensmittel ohne Zusätze!
        Beispielsweise nur für reine naturbelassene Sahne, jedoch nicht für
        Sahne mit Zusatzstoffen. Zusatzstoffe können sich auch in
        Grundnahrungsmitteln verstecken, wo man sie nicht vermuten würde. Lesen
        Sie daher stets die Zutatenliste auf der Verpackung.</span
      >

      <span
        display="inline-flex"
        justify="center"
        p="t-5 b-3"
        text="lg"
        font="semibold"
        >Wirkungsweise auf den Histaminstoffwechsel</span
      >
      <span p="b-3"
        >Die App dient als grobe Orientierungshilfe für die Einschätzung des
        Histaminpotentials, d.h. für die dosisabhängige und teils individuell
        unterschiedliche Verträglichkeit, welche durch verschiedene Mechanismen
        beeinflusst wird. Der Grund für die Unverträglichkeit ist in der
        Detailansicht mit folgenden Buchstaben angegeben:</span
      >
      <span m="b-1" p="y-1 x-3" font="semibold"
        >H!: Hoch Verderblich, rasche Histaminbildung</span
      >
      <span m="b-1" p="y-1 x-3" font="semibold">H: Hoher Histamingehalt</span>
      <span m="b-1" p="y-1 x-3" font="semibold">A: Andere biogene Amine</span>
      <span m="b-1" p="y-1 x-3" font="semibold"
        >L: Liberatoren von Mastzellmediatoren (=Histaminliberatoren)</span
      >
      <span m="b-1" p="y-1 x-3" font="semibold"
        >B: Blocker (=Hemmstoffe) der Diaminoxidase oder anderer Histamin
        abbauender Enzyme</span
      >
      <span p="y-3"
        >Je nach körperlicher Ursache sind nicht alle Lebensmittel für alle
        Betroffenen gleichermaßen unverträglich. Einige reagieren auf
        Liberatoren stärker als auf Histamin und umgekehrt. Halten Sie sich
        deshalb bloß zu Beginn ganz strikt an diese Verträglichkeitsliste.
        Beginnen Sie nach ca. 4-6 Wochen auszuprobieren, was Sie bei Ihrer
        individuellen Empfindlichkeit in welchen Mengen vertragen, um sich
        langfristig nicht unnötig einzuschränken.</span
      >

      <span
        display="inline-flex"
        justify="center"
        p="t-5 b-3"
        text="lg"
        font="semibold"
        >Haftungsausschluss</span
      >
      <span p="b-3"
        >Der Gebrauch dieser Informationen erfolgt auf eigene Verantwortung. Für
        direkte Schäden und Folgeschäden jeder Art kann keine Haftung übernommen
        werden.</span
      >
    </div>
  </div>
</template>
