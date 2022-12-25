<script setup>
import { ref, reactive } from "vue";
import QrcodeVue from "qrcode.vue";

let value = ref("hr://defaultdata.random");
let size = ref(100);

function upsize() {
  size.value = size.value + 100;
}

function random() {
  const result = Math.random().toString(36);
  value.value = "hr://" + result;
}
</script>

<template>
  <qrcode-vue :value="value" :size="size"></qrcode-vue>
  <br />
  <button v-on:click="upsize">Upsize</button>
  <br />
  <button v-on:click="random">Random</button>
</template>
