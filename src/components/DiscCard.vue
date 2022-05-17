<template>
 

  <div class="card-container">
    <div class="card-img">
      <img :src="discItem.poster" alt="">
    </div>
    <div class="card-text pt-2">
      <h4>{{discItem.title}}</h4>
      <h5>{{discItem.author}}</h5>
      <h6>{{discItem.year}}</h6>
    </div>
  </div>

</template>

<script>
export default {
  name: 'DiscCard',
  props:{
    discItem: Object
  }
}
</script>

<style lang="scss" scoped>
.card-container{
  background-color: #2c3742;
  padding: 10px;
  width: calc(100% / 5.5);
  margin-top: 10px;
}
.card-img{
  width: 100%;
  img{
    width: 100%;
  }
}
.card-text{
  text-align: center;
  h4{
    color: white;
    text-transform: uppercase;
  }
  h5, h6{
    color: #706e6f;
  }
}
</style>