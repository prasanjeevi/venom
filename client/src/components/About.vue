<template>
  <div>
    <h2>About</h2>
    <mindmap
      :nodes="nodes"
      :connections="connections"
      :editable="true"/>
  </div>
</template>

<script>
import map from './map.js'

export default {
  data () {
    return { ...map }
  }
}
</script>

<style>

</style>
