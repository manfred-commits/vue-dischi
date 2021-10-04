<template>
  <div id="app"> 
    <section class="container-page d-flex flex-wrap justify-content-center ">
      <Header 
      :image="headerImage" 
      :title="'Spotify logo'" 
      @artist="artistFilter"
      @genre="genreFilter"
      :selectValues="selectArray"/>
      <Albums 
      :genreType="selectedGenre"
      :artistSelect="selectedArtist"
      @select="selectArr"
      @author="selectAuth"/>
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
      selectedArtist:"",
      selectArray:[],
      selectArAuthor:[],
    }
  },
  methods:{
    genreFilter(selectedGenre){
      // console.log(selectedGenre);
      // console.log(this.selectedGenre);
      this.selectedGenre=selectedGenre;
      // console.log(this.selectedGenre);
      

    },
    artistFilter(selectedArtist){
      // console.log(selectedArtist);
      this.selectedArtist=selectedArtist;

    },
    selectAuth(selectA){
      // console.log(selectA);
      this.selectArAuthor=selectA;

    },
    selectArr(selectEl){
      // console.log(selectEl);
      // console.log(this.selectArray);
      this.selectArray=selectEl;
    }
  },
  
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
@import './assets/style/variables.scss';

</style>
