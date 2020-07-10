<template>
  <div id="app">
    <Home />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Home from "./components/index.vue";

@Component({
  components: {
    Home
  }
})
export default class App extends Vue {}
</script>

<style lang="scss">
@import "assets/scss/style.scss";
</style>
