<script setup lang="ts">
import {useRoute} from "vue-router";

definePageMeta({
  layout: "right-sidebar",
});

const route = useRoute()
</script>

<template>
  <div>items {{ route.params.idParam }}</div>
</template>

<style scoped>

</style>
