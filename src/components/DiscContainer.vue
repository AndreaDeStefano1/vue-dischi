<template>

  <div>

    <div v-if="isLoaded" class="container disc-container d-flex flex-wrap justify-content-between">
      <DiscCard 
      v-for="(disc,index) in discsArrayComputed" :key="`disc-${index}`"
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
    computed: {
      discsArrayComputed(){
        return this.discArray.filter( disc => (disc.genre == this.recivedGenre || this.recivedGenre == 'All') && (disc.author == this.recivedAuthor || this.recivedAuthor == 'All'))
        // 
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
          this.discArray = r.data.response;
          this.isLoaded = true;
        })
      }
    },
    props:{      
      recivedAuthor: String,
      recivedGenre: String,
    }
}
</script>

<style lang="scss" scoped>



</style>