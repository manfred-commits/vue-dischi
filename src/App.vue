<template>
  <div id="app">
    <Header :image="headerImage" :title="'Spotify logo'"/>
    <Albums/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Albums from './components/Albums.vue'


export default {
  name: 'App',
  components: {
    Header,
    Albums
  },
  data(){
    return{
      headerImage: require('./assets/images/spotify-logo.png'),
    }
  },
  
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
@import './assets/style/variables.scss';



</style>
