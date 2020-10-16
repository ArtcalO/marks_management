<template>
  <div id="app">
    <hr>
    <app-home></app-home>
    <hr>

  </div>
</template>

<script>
import Home from './components/Home.vue'
export default {

  components : {
    'app-home' : Home
  },
  data (){
    return{

    }
  }
  
};
</script>

<style>

</style>
