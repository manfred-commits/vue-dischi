<template>
    <header>
        <img :src="image" :alt="title">


        <select name="artist" v-model="currentArtist" @change="$emit('artist',currentArtist)">
            <option value="">Scegli un artista</option>
            <option v-for="(select,index) in authorValues" :key="index" :value="select">{{select}}</option>
        </select>


        <select name="genre" v-model="selectedGenre" @change="$emit('genre',selectedGenre)">
            <option value="">Scegli un genere</option>
            <option v-for="(select,index) in selectValues" :key="index" :value="select">{{select}}</option>
        </select>
    </header>
</template>

<script>
export default {
    name:'Header',
    props:['image','title', 'selectValues','authorValues'],
    data(){
        return{
            selectedGenre:"",
            currentArtist:"",
        }
    }
}
</script>

<style lang="scss" scope>

@import '../assets/style/variables.scss';

header{
    display: flex;
    justify-content: space-between;
    background-color: $header_background_color;
    width: 100%;
    height: 3.75rem;

    img{
        margin-left: 1.25rem;
        object-fit: contain;
        width: 3.5rem;
    }
    select{
        margin: 5px;
        margin-right: 15px;
    }

}
</style>