<template>
  <div class="ad-list">
    <ul>
      <li v-for="ad in ads" :key="ad.id">
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
import { PropType } from 'vue'

const props = defineProps({
  ads: {
    required: true,
    type: Array as PropType<Ad[]>,
  },
})
</script>

<style lang="scss" scoped>
.ad-list {
  max-width: 960px;
  margin: 40px auto;

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
  color: #17bf66;
  font-weight: bold;
  margin: 10px 4px;
}
</style>
