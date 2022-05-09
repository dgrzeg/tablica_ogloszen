<template>
  <div>
    <AdList :ads="ads" />
  </div>
</template>

<script lang="ts" setup>
import Ad from '@/types/Ad'
import AdList from './components/AdList.vue'
import { ref } from '@vue/reactivity'

const ads = ref<Ad[]>([
  {
    title: `sprzedam Opla`,
    location: `blok 12 m.9`,
    price: 1200,
    id: `1`,
  },
  {
    title: `proszę nie śmiecić i nie rzucać kiepów`,
    location: `na klatce w bloku 11`,
    price: 0,
    id: `2`,
  },
  {
    title: `kupię miejsce w garażu podziemnym`,
    location: `blok 12 m.1`,
    price: 25000,
    id: `3`,
  },
  {
    title: `tanio ziemniaki od rolnika`,
    location: `tel 111-111-111`,
    price: 12,
    id: `4`,
  },
  {
    title: `kupię Passata`,
    location: `blok 11 m.1`,
    price: 9999,
    id: `5`,
  },
])
</script>

<style lang="scss"></style>
