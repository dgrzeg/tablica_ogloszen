<template>
  <div class="ad-list">
    <p>Posortowane po - {{ order }}</p>
    <ul>
      <li v-for="ad in orderAds" :key="ad.id">
        <h2>{{ ad.title }} - {{ ad.location }}</h2>
        <div class="price">
          <p>{{ ad.price }}</p>
        </div>
        <div class="descsription">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Temporibus,
          at minus debitis nisi illo hic excepturi porro obcaecati doloremque
          sapiente.
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import Ad from '@/types/Ad'
import Order from '@/types/Order'
import { computed } from '@vue/reactivity'
import { PropType } from 'vue'

const props = defineProps({
  ads: {
    required: true,
    type: Array as PropType<Ad[]>,
  },
  order: {
    required: true,
    type: String as PropType<Order>,
  },
})

const orderAds = computed(() => {
  return [...props.ads].sort((a: Ad, b: Ad) => {
    return a[props.order] > b[props.order] ? 1 : -1
  })
})
</script>

<style lang="scss" scoped>
.ad-list {
  max-width: 960px;
  margin: 40px auto;
  color: #423430;
  & ul {
    padding: 0;
  }
  & li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  & h2 {
    margin: 0 0 10px;
  }
}
.price p {
  color: #6f5851;
  font-weight: bold;
  margin: 10px 4px;
}
</style>
