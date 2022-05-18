<template>
  <div>
    <HeaderComp 
    @searchForGenre='selectedGenreValue'
    @searchForAuthor='selectedAuthorValue'/>

    <MainComp 
    :discsGenre="valueToPass"
    :discsAuthor="valueToPass"
    />
  </div>
</template>

<script>

import MainComp from './components/MainComp.vue'
import HeaderComp from './components/HeaderComp.vue'


export default {
  name: 'App',
  components: {
    MainComp,
    HeaderComp
    
  },
  methods:{
    selectedGenreValue(value){
      console.log(value);
      this.valueToPass = value
    },
  
    selectedAuthorValue(value){
      console.log(value);
      this.valueToPass = value
    }
  },
  data(){
    return {

      valueToPass: 'All'
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/general'


</style>
