<template>
  <section class="albums"  >
      <Album v-for="(album,index) in albums" 
      :key="index" 
      :image="album.poster"
      :title="album.title"
      :author="album.author"
      :year="album.year"/>

  </section>
</template>

<script>

import Album from './Album.vue'
import axios from 'axios'

export default {
    name:'Albums',
    components:{
        Album,
    },
    data(){
        return{
            albums:[],
        }
    },
    created(){
    axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then( (response) => {
      console.log(response);
      this.albums=response.data.response;
      console.log(this.albums);

    });
  }

}
</script>

<style lang="scss" scope>
.albums{
    display: flex;
    flex-wrap: wrap;
    width: 70%;
    margin: auto;
    padding: 1.25rem;
    height: calc(100vh - 3.75rem);
}
</style>