<template>
  <div id="app">
    <!-- header con logo spotify  -->

    <BarraHeader />

    <select  v-model="valueOpt" class="form-select w-25 m-auto mt-3">
      <option selected>Select your genre</option>
      <option :value="elem" v-for="(elem, index) in genDischi" :key="index" >{{elem}}</option>
      
    </select>

    <!-- parte content  -->
    <main>
      <div id="width" class="container-fluid">
        <div class="d-flex justify-content-center flex-wrap p-5 gap">
          <MainContent v-for="(element, index) in dataDischi" :key="index" :card="element" />
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
      dataDischi: '',
      genDischi: [],
      valueOpt: '',
      // array response
    }

  },
  computed: {   
    
    
  

      },
  mounted() {

    this.getDischi();



  },
  methods: {
    getDischi() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
          this.dataDischi = response.data.response

          //Ciclo foreach per avere il genre degli album
          this.dataDischi.forEach((singleAlbum) => {


            // if  la condizione è true e quindi singleAlbum.genre non è già dentro (è presente "!"), lo pusha, se invece è già dentro risulta false e quindi non fa nulla, così nel ciclo pusherà il genere una sola volta

            if (!this.genDischi.includes(singleAlbum.genre)) {
              this.genDischi.push(singleAlbum.genre)
            }



          })
        })
    },





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
