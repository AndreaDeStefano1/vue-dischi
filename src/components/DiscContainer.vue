<template>

  <div>

    <div v-if="isLoaded" class="container disc-container d-flex flex-wrap justify-content-between">
      <DiscCard 
      v-for="(disc,index) in discArray" :key="`disc-${index}`"
      :discItem="disc"/>

    </div>
    <div v-else class="container">
    
      <LoaderComp/>
    </div>

  </div>

</template>

<script>
import DiscCard from './DiscCard.vue';
import axios from 'axios';
import LoaderComp from './LoaderComp.vue'
export default {
    name: "DiscContainer",
    data(){
      return{
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        discArray: [],
        isLoaded: false,
      }
    },
    components: { 
      DiscCard,
      LoaderComp
    },
    mounted(){
      setTimeout(this.getAPI, 3000)
      
    },
    methods:{
      getAPI (){
        axios.get(this.apiUrl)
        .then(r => {
          console.log(r.data.response)
          this.discArray = r.data.response;
          this.isLoaded = true;
        })
      }
    }
}
</script>

<style lang="scss" scoped>



</style>