<template>
    <header>
        <img :src="image" :alt="title">
        <select name="genre" v-model="selectedGenre" @change="$emit('genre',selectedGenre)">
            <option value="">Scegli un genere</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </header>
</template>

<script>
export default {
    name:'Header',
    props:['image','title'],
    data(){
        return{
            selectedGenre:"",
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