<script setup>
import { ref, reactive } from "vue";
import QrcodeVue from "qrcode.vue";

let value = ref("hr://somedata.lambda");
let size = ref(100);

function upsize() {
  size.value = size.value + 100;
}

function random() {
  value.value = "https://google.com";
}
</script>

<template>
  <qrcode-vue :value="value" :size="size"></qrcode-vue>
  <br />
  <button v-on:click="upsize">Upsize</button>
  <br />
  <button v-on:click="random">Random</button>
</template>
