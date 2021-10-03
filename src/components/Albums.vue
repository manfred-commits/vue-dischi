<template>
  <section class="albums my-2 gy-3 g-0 row row-cols-2 row-cols-md-5 row-cols-lg-5 justify-content-center align-self-start"  >
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
  width: 70%;
}
</style>