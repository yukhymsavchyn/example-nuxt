<script setup lang="ts">
import {onMounted, ref} from "vue";
import axios from 'axios'

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

// const asyncData = await useAsyncData(async () => {
  // const data: any = await axios.get('https://cat-fact.herokuapp.com/facts/')
  // console.log('useAsyncData', data.data.length)

  // return {
  //   data: data.data.length || 1
  // }
// })

onMounted(async () => {
  const data: any = await axios.get('https://cat-fact.herokuapp.com/facts/')
  dataFromServer.value = data.data.length
  console.log('onMounted', data.data.length)

  console.log('document', document.querySelector('header'))
})

const dataFromServer = ref('blabla')

const isValid = ref(false)

const data = computed(() => isValid.value ? 'yes its valid' : 'no its not valid')
</script>

<template>
  <header class="header">
    {{ dataFromServer }} async data
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
