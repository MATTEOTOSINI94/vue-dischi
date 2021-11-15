<template>
  
    
      <div class="col">
        <div id="card-style" class="card">
          <img :src="img" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">{{titolo}}</h5>
            <p class="card-text"> {{autore}}<br>{{year}}.</p>
            
          </div>
        </div>
      </div>
   
  
</template>

<script>
export default {
  name: "CardComponent",

  

  props:["img","titolo","autore","year"]
  
 
}


</script>


<style lang="scss">
#card-style{
  height: 100%;
  background: rgba(43, 58, 70, 0.705);
  padding-top: 20px;
  padding-bottom: 25px;

  img{
    width: 120px;
    align-self: center;
  }

  h5{
    color: white;
    text-align: center;
  }
  p{
    color: grey;
    text-align: center
  };
}
</style>


