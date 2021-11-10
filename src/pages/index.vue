<script setup lang="ts">
import ItemList from '~/components/ItemList.vue'
import Header from '~/components/Header.vue'
import Searchbar from '~/components/Searchbar.vue'
import UpdatePrompt from '~/components/UpdatePrompt.vue'
</script>

<template>
  <div display="flex" flex="col">
    <Header title="Histamin Ampel 🚥" />
    <Searchbar />
    <ItemList />
    <UpdatePrompt />
  </div>
</template>

<style></style>
