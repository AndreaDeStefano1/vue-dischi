<template>
  <div>
    <HeaderComp 
    @searchForGenre='selectedGenreValue'
    @searchForAuthor='selectedAuthorValue'/>

    <MainComp 
    :discsGenre="valueGenreToPass"
    :discsAuthor="valueAuthorToPass"
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
      this.valueGenreToPass = value
    },
  
    selectedAuthorValue(value){
      console.log(value);
      this.valueAuthorToPass = value
    }
  },
  data(){
    return {

      valueGenreToPass: 'All',
      valueAuthorToPass: 'All'

    }
  }
}
</script>

<style lang="scss">
@import './assets/style/general'


</style>
