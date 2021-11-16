<template>
  <main>
      <div class= "main-container">
          <div class="container pb-5">
               
            <SelectBar @searchGenre="findValue"></SelectBar>
            
              <div  class="row row-cols-1 row-cols-md-5 g-5 m-0">
              <CardComponent v-for="element,i in filterCards" :key="i"
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
import SelectBar from '../components/selectComponent.vue'
export default {
    name:"Main",
    components:{
        CardComponent,
        Loader,
        SelectBar
    },

    data(){
    return {
        arrayVuoto:[],
        boolean:true,
        selectedGenre:"all"

    }
},
computed:{
    filterCards(){
        console.log()
        return this.arrayVuoto.filter((element)=>{
            
            if (element.genre === this.selectedGenre || this.selectedGenre === "all") {
                return true
               
            }
        })
    }
},
methods:{

    findValue(selected){
        this.selectedGenre = selected

    },

   fetchArray(){
       axios.get("https://flynn.boolean.careers/exercises/api/array/music").then((elemento) =>{
            this.arrayVuoto = elemento.data.response
            console.log(this.arrayVuoto)
            setInterval(() => {
                this.boolean = false
            }, 2000);

        })
   }

},
mounted(){
        this.fetchArray()

    }
}




</script>

<style>
    .main-container{
        min-height: 100vh;
        background: rgb(25, 45, 59);
    }
</style>