<template>
    <section class="album">
        <img  :src="image" :alt="title">
        <div class="albums-text">
            <h3>{{title}}</h3>
            <h4>{{author}}</h4>
            <h6>{{year}}</h6>
        </div>
    </section>
    
</template>

<script>

export default {
    name:'Album',
    props:[ 'image','author','title','year']
    
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables.scss';


.album{
    background-color: $album_background_color;
    width: calc(100% / 5 - 2.50rem);
    margin: .625rem 1.25rem;
    text-align: center;
    img{
        padding: .125rem;
        object-fit: contain;
        width: 100%;
    }


    .albums-text{

        h3{
            font-size: 20px;
            color: $primary_album_h3_color;
        }
        h4,h6{
            font-size: .875rem;
            color: $secondary_album_text_color;
        }
    }
}
</style>