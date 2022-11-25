<template>
  <div id="app" class="bg-dark">
    
    <BarraHeader />
    <MainContent />
  </div>
</template>

<script>
import BarraHeader from './components/BarraHeader.vue'
import MainContent from './components/MainContent.vue'

export default {
  name: 'App',
  components: {
    BarraHeader,
    MainContent
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
