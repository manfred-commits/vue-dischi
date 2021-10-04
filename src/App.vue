<template>
  <div id="app"> 
    <section class="container-page d-flex flex-wrap justify-content-center ">
      <Header :image="headerImage" :title="'Spotify logo'" @genre="genreFilter"/>
      <Albums :genreType="selectedGenre"/>
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
      selectedGenre: "",
    }
  },
  methods:{
    genreFilter(selectedGenre){
      // console.log(selectedGenre);
      // console.log(this.selectedGenre);
      this.selectedGenre=selectedGenre;
      // console.log(this.selectedGenre);


    }
  }
  
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
@import './assets/style/variables.scss';

</style>
