<template>
  <div>

    
    <div class="calc">
      
     
        <div class="card text-white p-4" style="width: 18rem">
          <img :src="card.poster" class="card-img-top" alt="..." />
          <div class="card-body">
            <h5 class="card-title">{{card.title}}</h5>
            <p class="card-text text-secondary">
                {{card.author}} <br>
                {{card.year}}
            </p>
          </div>
        
      </div>
    </div>
  </div>
</template>


<script>
  export default {
    name: 'MainContent',
    props: {
      card: Object
    }
    
  }
</script>

  
  <style scoped lang="scss">



  .card-title {
    text-transform: uppercase;
  }
.card {
  width: calc(100% / 5);
  height: 350px;
  background-color: #2E3A46;
  
}

img {
    height: 180px;
    width: 200px;
    align-self: center;
  }




  
  </style>