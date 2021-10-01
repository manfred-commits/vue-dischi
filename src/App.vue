<template>
  <div id="app">
    <Header/>
    <Albums/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Albums from './components/Albums.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    Header,
    Albums
  },
  created(){
    axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then( (response) => {
      console.log(response);
    });
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
@import './assets/style/variables.scss';



</style>
