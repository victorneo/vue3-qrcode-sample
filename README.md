# Vue 3 QR Code

Samples for using a QR Code Generator and Reader with Vue 3.


## Using The Samples

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

## QRGenerator.vue

See `src/components/QRGenerator.vue`.

We use [qrcode.vue](https://github.com/scopewu/qrcode.vue) to generate QR Codes.

To install, use the following command:

```
npm install --save qrcode.vue
```


## QRReader.vue

See `src/components/QRReader.vue`.

We use [vue-qrcode-reader](https://github.com/gruhn/vue-qrcode-reader) to
access the camera and read QR Codes.

Note: the current default version does not work with Vue 3. You need to use a special version to use this library with Vue 3.
See [this comment on GitHub](https://github.com/gruhn/vue-qrcode-reader/issues/203#issuecomment-1032569533) for more information.

To install the Vue 3 compatible version, use the following command:

```
npm install --save-exact vue-qrcode-reader@3.1.0-vue3-compatibility.2
```
