<script setup>
import ProjectDetail from "../components/ProjectDetail.vue";
</script>

<template>
  <main ><ProjectDetail /></main>
</template>

<style scoped>
main {
    padding: 0;
  }
@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    display: flex;
    align-items: center;

  }
}
</style>
