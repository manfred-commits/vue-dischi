<template>
  <section class="albums my-1 gy-3 g-0 row row-cols-1 row-cols-md-2 row-cols-lg-5 justify-content-center align-self-start"  >
      <Album v-for="(album,index) in albumFilter" 
      :key="index" 
      :album="album"/>

  </section>
</template>

<script>

import Album from './Album.vue'
import axios from 'axios'

export default {
    name:'Albums',
    props:['genreType','artistSelect'],
    components:{
        Album,
        
    },
    
    data(){
        return{
            albums:[],
            iconCategories:[],
            authorCategories:[]
        }
    },
    methods:{
      selectFiller(){
        // console.log("ciao");
        // console.log(this.albums);
        this.albums.forEach(
          (element) => {
            // console.log("ciao");

            if(!this.iconCategories.includes(element.genre)){
                this.iconCategories.push(element.genre);
                // console.log("ciao");
            }
          }
        );
      },
      selectAuthor(){
        // console.log("ciao");
        // console.log(this.albums);
        this.albums.forEach(
          (element) => {
            // console.log("ciao");

            if(!this.authorCategories.includes(element.author)){
                this.authorCategories.push(element.author);
                // console.log("ciao");
            }
          }
        );
      }
    },
    computed:{
      albumFilter(){
        const albumsFiltered = this.albums.filter(
          (element)=>{
            // console.log(element.genre);
            
            // console.log(this.genreType);

            // console.log(element.genre.toLowerCase());
            // console.log(this.genreType.toLowerCase());


            // console.log(element.genre.toLowerCase().includes(this.genreType.toLowerCase()));
            return element.genre.toLowerCase().includes(this.genreType.toLowerCase()) && element.author.toLowerCase().includes(this.artistSelect.toLowerCase());

           

          }
        );
      
      return albumsFiltered;
      },
      
    },
    created(){

    axios
    .get("https://flynn.boolean.careers/exercises/api/array/music")
    .then( (response) => {
      // console.log(response);
      this.albums=response.data.response;
      // console.log(this.albums);
      this.selectFiller();
      this.selectAuthor();

      // console.log(this.iconCategories);
      this.$emit('author',this.authorCategories);

      this.$emit('select',this.iconCategories);
    })
  }

}
</script>

<style lang="scss" scope>
.albums{
  width: 70%;
}
</style>