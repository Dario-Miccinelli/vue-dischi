<template>
  <div id="app">
    <!-- header con logo spotify  -->

    <BarraHeader />

    <!-- parte content  -->
    <main>
      <div id="width" class="container-fluid">
      <div class="d-flex justify-content-center flex-wrap p-5 gap">
    <MainContent v-for="(element, index) in dataDischi" :key="index" :card="element"/> 
    </div>
    </div>

  </main>
    

  </div>
</template>


<!-- import part -->
<script>
import axios from 'axios';
import BarraHeader from './components/BarraHeader.vue'
import MainContent from './components/MainContent.vue'



export default {
 
  name: 'App',
  components: {
    BarraHeader,
    MainContent,


  },
  data() {
    return {
      dataDischi: '' 
      // array reponse
    }

  },
  mounted() {

    this.getDischi();



  },
  methods: {
    getDischi() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
          .then((response) => {
            this.dataDischi = response.data.response
          
          })
      }
    


  }
}




</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
 
  text-align: center;
  height: 100vh;
  background-color: rgb(30, 45, 59);
}


#width {
  width: 90%;
}

.gap {
  gap: 20px;
}

* {
  margin: 0;
}
</style>
