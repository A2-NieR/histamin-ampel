<script setup lang="ts">
import ItemList from '~/components/ItemList.vue'
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import Searchbar from '~/components/Searchbar.vue'
</script>

<template>
  <div h="screen" display="flex" flex="col">
    <Header title="Histamin Ampel 🚥" />
    <Searchbar />
    <ItemList p="b-12" />
    <!-- <Footer /> -->
  </div>
</template>

<style></style>
