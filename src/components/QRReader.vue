<script setup>
import { ref, reactive } from "vue";
import { QrcodeStream, QrcodeDropZone, QrcodeCapture } from "vue-qrcode-reader";

let text = ref("");

function onDecode(decodedString) {
  text.value = decodedString;
}

async function onInit(promise) {
  try {
    const { capabilities } = await promise;
    // successfully initialized
  } catch (error) {
    if (error.name === "NotAllowedError") {
      text.value = "Denied! No permission";
      // user denied camera access permisson
    } else if (error.name === "NotFoundError") {
      // no suitable camera device installed
    } else if (error.name === "NotSupportedError") {
      // page is not served over HTTPS (or localhost)
    } else if (error.name === "NotReadableError") {
      // maybe camera is already in use
    } else if (error.name === "OverconstrainedError") {
      // did you requested the front camera although there is none?
    } else if (error.name === "StreamApiNotSupportedError") {
      // browser seems to be lacking features
    }
  } finally {
    // hide loading indicator
  }
}
</script>

<template>
  <qrcode-stream :key="_uid" @init="onInit" @decode="onDecode" />
  <br />
  <p>{{ text }}</p>
</template>
