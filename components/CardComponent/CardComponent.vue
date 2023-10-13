<script setup lang="ts">
import { CardProperties } from "~/components/CardComponent/types";
import { useRouter } from 'vue-router'

defineProps<CardProperties>()

const router = useRouter()
const onClick = (label: string) => {
  router.push('/items/' + label)
}
</script>

<template>
  <div class="card" @click="onClick(label)">
    <p v-html="label" />
    <p>{{ price }}</p>
    <div>{{ options }}</div>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid black;
  padding: 10px;
  margin: 10px;
}
</style>
