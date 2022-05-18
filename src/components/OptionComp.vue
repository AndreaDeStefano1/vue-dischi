<template>
  <option :value="discItem">
    {{discItem}}
  </option>
</template>

<script>

export default {
  name: 'OptionComp',
  props:{
    discItem: String,
  }
}
</script>

<style>

</style>