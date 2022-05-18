<template>
  <div id="app">
    <!-- <headerComp /> -->
    
    <mainComp />
  </div>

</template>

<script>
import axios from 'axios'
// import headerComp from './components/headerComp.vue'
import mainComp from './components/mainComp.vue'


export default {
  name: 'App',
  components: {
    // headerComp,
    mainComp,
  },

  data(){
     return{
     baseURL: 'https://flynn.boolean.careers/exercises/api/array/music',
     datasMusic: [],
    }
  },

  mounted(){
     axios.get(this.baseURL)
     .then(response => {
       this.datasMusic = response.data.response;
       console.log(this.datasMusic);
    })
  }

}
</script>

<style lang="scss">

  @import './assets/style/general';

</style>
