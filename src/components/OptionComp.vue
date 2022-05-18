<template>
  <option :value="value">
    {{value}}
  </option>
</template>

<script>

export default {
  name: 'OptionComp',
  props:{
    value: String,
  }
}
</script>

<style>

</style>