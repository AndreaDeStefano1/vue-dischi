<template>
  <main class="py-5">

    <DiscContainer 
    :recivedGenre="discsGenre"
    :recivedAuthor="discsAuthor"    
    />

  </main>
</template>

<script>
import DiscContainer from './DiscContainer.vue';
 
export default {
  name: 'MainComp',
  components:{
    DiscContainer,
  },
  props: {
    discsGenre: String,
    discsAuthor: String
  },
}
</script>

<style>
main{
  background-color: #1e2d3b;
  height: 100vh;
}
</style>