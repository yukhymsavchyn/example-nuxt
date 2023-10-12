<template>
    <div class="layout">
      <Header />
      <div class="content">
        <slot></slot>
      </div>
      <Footer />
  </div>
</template>
<script setup lang="ts">
import Header from "~/components/base/header.vue";
import Footer from "~/components/base/footer.vue";
</script>

<style>
.layout {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.content {
  padding: 20px;
  flex: 1;
}
</style>
