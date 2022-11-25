<template>
  <div id="app" >
    
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
  height: 100vh;
  background-color: rgb(30, 45, 59);
}

* {
  margin: 0;
}
</style>
