<template>
  <div>
    <header>
      <div class="order">
        <button @click="handleOrder('title')">sortuj po tytule</button>
        <button @click="handleOrder('price')">sortuj po cenie</button>
        <button @click="handleOrder('location')">sortuj po lokacji</button>
      </div>
    </header>
    <AdList :ads="ads" :order="order" />
  </div>
</template>

<script lang="ts" setup>
import Ad from '@/types/Ad'
import Order from '@/types/Order'
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
    title: `wynajmę miejsce w garażu podziemnym`,
    location: `blok 12 m.1`,
    price: 200,
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

const order = ref<Order>('title')

const handleOrder = (orderParam: Order) => {
  order.value = orderParam
}
</script>

<style lang="scss">
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
