<template>
  <div id="app">
    <headerComp />
    
    <mainComp />
  </div>

</template>

<script>
import headerComp from './components/headerComp.vue'
import mainComp from './components/mainComp.vue'


export default {
  name: 'App',
  components: {
    headerComp,
    mainComp
  }
}
</script>

<style lang="scss">

  @import './assets/style/general';

</style>
