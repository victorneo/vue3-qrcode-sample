<script setup>
import QRGenerator from "./components/QRGenerator.vue";
import QRReader from "./components/QRReader.vue";
import { ref, computed } from "vue";

const routes = {
  "/": QRGenerator,
  "/read": QRReader,
};

const currentPath = ref(window.location.hash);

window.addEventListener("hashchange", () => {
  currentPath.value = window.location.hash;
});

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || "/"] || NotFound;
});
</script>

<template>
  <main>
    <a href="#/">QR Generator</a> | <a href="#/read">QR Reader</a> |
    <component :is="currentView" />
  </main>
</template>

<style scoped>
main {
  margin-left: auto;
  margin-right: auto;
  width: 75%;
}
</style>
