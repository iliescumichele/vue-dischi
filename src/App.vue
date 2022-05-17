<template>
  <div id="app">
    <headerComp />
    
    <mainComp />
  </div>

</template>

<script>
import axios from 'axios'
import headerComp from './components/headerComp.vue'
import mainComp from './components/mainComp.vue'


export default {
  name: 'App',
  components: {
    headerComp,
    mainComp,
  },

  data(){
     return{
     baseURL: 'https://flynn.boolean.careers/exercises/api/array/music',
     array: [],
    }
  },

  mounted(){
       axios.get(this.baseURL)
       .then(response => {
         this.array = response.data.response;
         console.log(this.array);
      })
  }

}
</script>

<style lang="scss">

  @import './assets/style/general';

</style>
