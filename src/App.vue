<template>
  <div id="app">
  <ChromeExt />
  </div>
</template>

<script lang="ts">
import ChromeExt from "./layouts/ChromeExt.vue";
// import Vue from 'vue';

export default ({
  name: 'App',
  components: {
    ChromeExt
  }
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
