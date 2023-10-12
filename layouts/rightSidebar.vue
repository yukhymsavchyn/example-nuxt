<template>
  <div class="layout">
    <Header />
    <div class="content">
      <div class="content__main">
        <slot></slot>
      </div>
      <div class="right-sidebar">
        right-sidebar
      </div>
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
  display: flex;
}

.content__main {
  flex: 1;
}

.right-sidebar {
  padding: 20px;
  border-left: 2px solid black;
}
</style>
