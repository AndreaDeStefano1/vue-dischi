<template>
  <div>
    <HeaderComp/>
    <MainComp/>
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
    
}
}
</script>

<style lang="scss">
@import './assets/style/general'


</style>
