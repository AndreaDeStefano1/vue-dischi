<template>
  <main class="py-5">

    <DiscContainer/>

  </main>
</template>

<script>
import DiscContainer from './DiscContainer.vue';
 
export default {
  name: 'MainComp',
  components:{
    DiscContainer,
  }
}
</script>

<style>
main{
  background-color: #1e2d3b;
  height: 100vh;
}
</style>