<script setup lang="ts">
import {onMounted, ref} from "vue";

const links = [
  {
    label: 'home',
    link: '/'
  },
  {
    label: 'about',
    link: '/about'
  },
  {
    label: 'items/1',
    link: '/items/1'
  }
]

useAsyncData(async () => {
  console.log('useAsyncData')

  return {}
})

onMounted(() => {
  console.log('onMounted')
})

const isValid = ref(false)

const data = computed(() => isValid.value ? 'yes its valid' : 'no its not valid')
</script>

<template>
  <header class="header">
    <nav class="header__nav">
      <nuxt-link v-for="(link, index) in links" class="header__link" :key="index" :to="link.link">{{ link.label }}</nuxt-link>
    </nav>
    <button @click="isValid = !isValid">toggle isValid</button>
    {{ data }} {{ isValid }}
  </header>
</template>

<style scoped>
.header {
  padding: 20px;
  border-bottom: 2px solid black;
}

.header__link {
  padding: 10px;
}
</style>
