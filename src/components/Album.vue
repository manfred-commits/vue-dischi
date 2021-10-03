<template>
    <section class="album px-1 py-2 ">
        <div class="inner-container d-flex flex-wrap align-items-start justify-content-center">
            <img  :src="image" :alt="title">
            <div class="albums-text">
                <h3>{{title}}</h3>
                <h4>{{author}}</h4>
                <h6>{{year}}</h6>
            </div>

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

    .inner-container{

        background-color: $album_background_color;
        height: 100%;
        text-align: center;
        padding: .9375rem;

        img{

            object-fit: contain;
            width: 100%;
        }


        .albums-text{

            h3{
                font-size: 1.25rem;
                color: $primary_album_h3_color;
            }
            h4,h6{
                font-size: .875rem;
                color: $secondary_album_text_color;
            }
        }
    }
    
}
</style>