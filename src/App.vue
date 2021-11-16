<template>
  <div id="app">

    <Header></Header>
    <Main></Main>
    
  </div>
</template>

<script>

import Header from './components/header.vue'
import Main from './components/main.vue'

export default {
  name: 'App',
  components: {
   Header,
   Main,
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap"; 

#app {
 
}
</style>
