<script setup lang="ts">
import CardComponent from "~/components/CardComponent/CardComponent.vue";

const cards = ref([
  {
    label: '<span style="background: red">ssss</span>',
    price: 111,
    options: [{ a: 1, b: 2, c: 3 }]
  },
])
</script>

<template>
  <div>
    <p>about</p>
    <div>
      <CardComponent
          v-for="(card, index) in cards"
          :key="index"
          :label="card.label"
          :price="card.price"
          :options="card.options"
      />
    </div>
  </div>
</template>

<style scoped>

</style>
