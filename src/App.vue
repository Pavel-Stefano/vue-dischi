<template>
  <div id="app">
    <app-header />
    <main>
      <main-grid />
    </main>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import MainGrid from './components/MainGrid.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    MainGrid,
  }
}
</script>

<style lang="scss">
@import "./style/generals";

#app {
  height: 100vh;
}

</style>
