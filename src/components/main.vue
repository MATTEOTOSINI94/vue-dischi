<template>
  <main>
      <div class= "main-container pb-5">
          <div class="container">
               <div  class="row row-cols-1 row-cols-md-5 g-5 m-0">
              <CardComponent v-for="element,i in arrayVuoto" :key="i"
              :img="element.poster"
              :titolo="element.title"
              :autore="element.author"
              :year="element.year"
              ></CardComponent>
               </div>
          </div>
          <Loader v-if="boolean === true"></Loader>
      </div>
  </main>
</template>

<script>
import axios from "axios"
import CardComponent from '../components/cardComponente.vue'
import Loader from '../components/loader.vue'
export default {
    name:"Main",
    components:{
        CardComponent,
        Loader
    },

    data(){
    return {
        arrayVuoto:[],
        boolean:true
        
    }
},
mounted(){
    
    
        axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((elemento) =>{
            this.boolean = false
            this.arrayVuoto = elemento.data.response
            console.log(this.arrayVuoto)
            
        })

    }
}




</script>

<style>
    .main-container{
       
        background: rgb(25, 45, 59);
    }
</style>