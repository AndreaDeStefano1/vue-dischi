<template>

  <div>

    <div class="container disc-container d-flex flex-wrap justify-content-between">
      <DiscCard 
      v-for="(disc,index) in discArray" :key="`disc-${index}`"
      :discItem="disc"/>

    </div>

  </div>

</template>

<script>
import DiscCard from './DiscCard.vue';
import axios from 'axios';

export default {
    name: "DiscContainer",
    data(){
      return{
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        discArray: [],
      }
    },
    components: { 
      DiscCard
    },
    mounted(){
      this.getAPI()
    },
    methods:{
      getAPI (){
        axios.get(this.apiUrl)
        .then(r => {
          console.log(r.data.response)
          this.discArray = r.data.response;
        })
      }
    }
}
</script>

<style lang="scss" scoped>



</style>