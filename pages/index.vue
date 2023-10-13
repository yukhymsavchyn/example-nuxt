<script setup lang="ts">
import CardComponent from "~/components/CardComponent/CardComponent.vue";
import { CardProperties } from "~/components/CardComponent/types";

const cards = ref<CardProperties[]>([
  {
    label: 'label1',
    price: 111,
    options: { a: 1, b: 2, c: 3 }
  },
  {
    label: 'label2',
    price: 222,
    options: { a: 1, b: 2, c: 3 }
  },
  {
    label: 'label3',
    price: 333,
    options: { a: 1, b: 2, c: 3 }
  }
])
</script>

<template>
  <div>
    <CardComponent
        v-for="(card, index) in cards"
        :key="index"
        :label="card.label"
        :price="card.price"
        :options="card.options"
    />
  </div>
</template>

<style scoped>
</style>
