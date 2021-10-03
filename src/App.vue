<template>
  <div id="app"> 
    <section class="container-page d-flex flex-wrap justify-content-center ">
      <Header :image="headerImage" :title="'Spotify logo'"/>
      <Albums/>

    </section>
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
