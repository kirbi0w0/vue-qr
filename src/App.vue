<script setup>
  import QRScanner from './components/QRScanner.vue';

function onScan (decodedText, decodedResult) {
      console.log('decodedText =>', decodedText)
      console.log('decodedResult =>', decodedResult)
    }
</script>

<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <QRScanner 
  :qrbox="250" 
  :fps="10" 
  style="width: 500px;"
  @result="onScan"
  />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
