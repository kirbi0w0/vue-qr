<template lang="">
    <div id="qr-code-full-region"></div>
</template>
<script setup>
import { onMounted } from 'vue';
import {Html5QrcodeScanner} from 'html5-qrcode'
const emit = defineEmits(['result'])
let html5QrcodeScanner = null
 const props = defineProps({
    qrbox: {
    type: Number,
    default: 250
  },
  fps: {
    type: Number,
    default: 10
  }
 })

 onMounted(() => {
    const config = {
      fps: props.fps,
      qrbox: props.qrbox,
    };
     html5QrcodeScanner = new Html5QrcodeScanner('qr-code-full-region', config);
    html5QrcodeScanner.render(onScanSuccess);
  })

  function  onScanSuccess (decodedText, decodedResult) {
      emit('result', decodedText, decodedResult);
    }
</script>
